# API Integration Skill

## Overview
Comprehensive expertise in integrating AI APIs and SDKs into enterprise development workflows, covering authentication, error handling, performance optimization, and multi-provider strategies.

## Core Integration Patterns

### Authentication Methods

**API Key Authentication:**
```python
import os
from openai import OpenAI

# Load from environment variable (recommended)
client = OpenAI(api_key=os.environ.get("OPENAI_API_KEY"))

# Never hardcode API keys
# BAD: client = OpenAI(api_key="sk-1234567890abcdef")
```

**OAuth 2.0 Integration:**
```python
import requests
from oauthlib.oauth2 import BackendApplicationClient
from requests_oauthlib import OAuth2Session

# Client credentials flow for service-to-service
client = BackendApplicationClient(client_id=CLIENT_ID)
oauth = OAuth2Session(client=client)
token = oauth.fetch_token(
    token_url="https://provider.com/oauth/token",
    client_id=CLIENT_ID,
    client_secret=CLIENT_SECRET
)
```

**SSO/SAML Integration:**
- Configure SAML 2.0 with enterprise IdP (Okta, Azure AD)
- Map user attributes to AI tool roles
- Implement Just-In-Time (JIT) provisioning
- Handle session management and token refresh

### Error Handling Patterns

**Retry with Exponential Backoff:**
```python
import time
from functools import wraps
from typing import TypeVar, Callable

T = TypeVar('T')

def retry_with_backoff(
    max_retries: int = 3,
    base_delay: float = 1.0,
    max_delay: float = 60.0,
    exponential_base: float = 2.0,
    retryable_exceptions: tuple = (Exception,)
) -> Callable[[Callable[..., T]], Callable[..., T]]:
    """Retry decorator with exponential backoff."""
    def decorator(func: Callable[..., T]) -> Callable[..., T]:
        @wraps(func)
        def wrapper(*args, **kwargs) -> T:
            last_exception = None
            for attempt in range(max_retries):
                try:
                    return func(*args, **kwargs)
                except retryable_exceptions as e:
                    last_exception = e
                    if attempt < max_retries - 1:
                        delay = min(
                            base_delay * (exponential_base ** attempt),
                            max_delay
                        )
                        time.sleep(delay)
            raise last_exception
        return wrapper
    return decorator

@retry_with_backoff(max_retries=3, retryable_exceptions=(TimeoutError,))
def call_ai_api(prompt: str) -> str:
    # API call implementation
    pass
```

**Circuit Breaker Pattern:**
```python
from datetime import datetime, timedelta
from enum import Enum
from threading import Lock

class CircuitState(Enum):
    CLOSED = "closed"
    OPEN = "open"
    HALF_OPEN = "half_open"

class CircuitBreaker:
    def __init__(
        self,
        failure_threshold: int = 5,
        recovery_timeout: int = 60,
        expected_exception: type = Exception
    ):
        self.failure_threshold = failure_threshold
        self.recovery_timeout = recovery_timeout
        self.expected_exception = expected_exception
        self.failure_count = 0
        self.last_failure_time = None
        self.state = CircuitState.CLOSED
        self.lock = Lock()

    def call(self, func, *args, **kwargs):
        with self.lock:
            if self.state == CircuitState.OPEN:
                if self._should_attempt_reset():
                    self.state = CircuitState.HALF_OPEN
                else:
                    raise Exception("Circuit is OPEN")

        try:
            result = func(*args, **kwargs)
            self._on_success()
            return result
        except self.expected_exception as e:
            self._on_failure()
            raise

    def _should_attempt_reset(self) -> bool:
        return (
            self.last_failure_time and
            datetime.now() - self.last_failure_time >
            timedelta(seconds=self.recovery_timeout)
        )

    def _on_success(self):
        with self.lock:
            self.failure_count = 0
            self.state = CircuitState.CLOSED

    def _on_failure(self):
        with self.lock:
            self.failure_count += 1
            self.last_failure_time = datetime.now()
            if self.failure_count >= self.failure_threshold:
                self.state = CircuitState.OPEN
```

### Rate Limiting

**Token Bucket Implementation:**
```python
import time
from threading import Lock

class TokenBucket:
    """Rate limiter using token bucket algorithm."""

    def __init__(self, tokens_per_second: float, max_tokens: int):
        self.tokens_per_second = tokens_per_second
        self.max_tokens = max_tokens
        self.tokens = max_tokens
        self.last_update = time.time()
        self.lock = Lock()

    def acquire(self, tokens: int = 1) -> bool:
        with self.lock:
            now = time.time()
            # Add new tokens based on elapsed time
            self.tokens = min(
                self.max_tokens,
                self.tokens + (now - self.last_update) * self.tokens_per_second
            )
            self.last_update = now

            if self.tokens >= tokens:
                self.tokens -= tokens
                return True
            return False

    def wait_for_token(self, tokens: int = 1):
        while not self.acquire(tokens):
            time.sleep(0.1)

# Usage
rate_limiter = TokenBucket(tokens_per_second=10, max_tokens=100)

def rate_limited_call(prompt: str):
    rate_limiter.wait_for_token()
    return call_ai_api(prompt)
```

## Multi-Provider Strategies

### Provider Abstraction Layer

```python
from abc import ABC, abstractmethod
from typing import Optional, List, Dict, Any
from dataclasses import dataclass

@dataclass
class AIResponse:
    content: str
    model: str
    provider: str
    tokens_used: int
    latency_ms: float

class AIProvider(ABC):
    """Abstract base class for AI providers."""

    @abstractmethod
    def complete(self, prompt: str, **kwargs) -> AIResponse:
        pass

    @abstractmethod
    def health_check(self) -> bool:
        pass

class OpenAIProvider(AIProvider):
    def __init__(self, api_key: str, model: str = "gpt-4"):
        from openai import OpenAI
        self.client = OpenAI(api_key=api_key)
        self.model = model

    def complete(self, prompt: str, **kwargs) -> AIResponse:
        import time
        start = time.time()
        response = self.client.chat.completions.create(
            model=self.model,
            messages=[{"role": "user", "content": prompt}],
            **kwargs
        )
        latency = (time.time() - start) * 1000
        return AIResponse(
            content=response.choices[0].message.content,
            model=self.model,
            provider="openai",
            tokens_used=response.usage.total_tokens,
            latency_ms=latency
        )

    def health_check(self) -> bool:
        try:
            self.client.models.list()
            return True
        except Exception:
            return False

class AnthropicProvider(AIProvider):
    def __init__(self, api_key: str, model: str = "claude-3-5-sonnet-20241022"):
        from anthropic import Anthropic
        self.client = Anthropic(api_key=api_key)
        self.model = model

    def complete(self, prompt: str, **kwargs) -> AIResponse:
        import time
        start = time.time()
        response = self.client.messages.create(
            model=self.model,
            max_tokens=kwargs.get("max_tokens", 4096),
            messages=[{"role": "user", "content": prompt}]
        )
        latency = (time.time() - start) * 1000
        return AIResponse(
            content=response.content[0].text,
            model=self.model,
            provider="anthropic",
            tokens_used=response.usage.input_tokens + response.usage.output_tokens,
            latency_ms=latency
        )

    def health_check(self) -> bool:
        try:
            # Simple health check
            return True
        except Exception:
            return False
```

### Failover Strategy

```python
class ProviderManager:
    """Manages multiple AI providers with failover."""

    def __init__(self, providers: List[AIProvider]):
        self.providers = providers
        self.primary_index = 0

    def complete(self, prompt: str, **kwargs) -> AIResponse:
        """Try each provider in order until one succeeds."""
        errors = []
        for i, provider in enumerate(self.providers):
            try:
                if not provider.health_check():
                    continue
                return provider.complete(prompt, **kwargs)
            except Exception as e:
                errors.append(f"{type(provider).__name__}: {e}")
                continue

        raise Exception(f"All providers failed: {errors}")

    def complete_with_fallback(
        self,
        prompt: str,
        fallback_prompt: Optional[str] = None,
        **kwargs
    ) -> AIResponse:
        """Try primary with fallback to simpler prompt."""
        try:
            return self.complete(prompt, **kwargs)
        except Exception as primary_error:
            if fallback_prompt:
                try:
                    return self.complete(fallback_prompt, **kwargs)
                except Exception:
                    pass
            raise primary_error
```

## Caching Strategies

### Response Caching

```python
import hashlib
import json
from typing import Optional
from datetime import datetime, timedelta

class ResponseCache:
    """Simple in-memory cache for AI responses."""

    def __init__(self, ttl_seconds: int = 3600):
        self.cache: Dict[str, tuple] = {}
        self.ttl = timedelta(seconds=ttl_seconds)

    def _make_key(self, prompt: str, model: str, **kwargs) -> str:
        """Create cache key from prompt and parameters."""
        key_data = json.dumps({
            "prompt": prompt,
            "model": model,
            **kwargs
        }, sort_keys=True)
        return hashlib.sha256(key_data.encode()).hexdigest()

    def get(self, prompt: str, model: str, **kwargs) -> Optional[str]:
        key = self._make_key(prompt, model, **kwargs)
        if key in self.cache:
            response, timestamp = self.cache[key]
            if datetime.now() - timestamp < self.ttl:
                return response
            del self.cache[key]
        return None

    def set(self, prompt: str, model: str, response: str, **kwargs):
        key = self._make_key(prompt, model, **kwargs)
        self.cache[key] = (response, datetime.now())

    def invalidate(self, prompt: str, model: str, **kwargs):
        key = self._make_key(prompt, model, **kwargs)
        self.cache.pop(key, None)
```

### Embedding Cache with Vector Storage

```python
import numpy as np
from typing import List, Tuple

class EmbeddingCache:
    """Cache embeddings for similarity search."""

    def __init__(self, similarity_threshold: float = 0.95):
        self.embeddings: List[np.ndarray] = []
        self.texts: List[str] = []
        self.responses: List[str] = []
        self.threshold = similarity_threshold

    def _cosine_similarity(self, a: np.ndarray, b: np.ndarray) -> float:
        return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))

    def find_similar(
        self,
        embedding: np.ndarray
    ) -> Optional[Tuple[str, float]]:
        """Find cached response for similar query."""
        best_score = 0
        best_response = None

        for i, cached_embedding in enumerate(self.embeddings):
            score = self._cosine_similarity(embedding, cached_embedding)
            if score > best_score and score >= self.threshold:
                best_score = score
                best_response = self.responses[i]

        return (best_response, best_score) if best_response else None

    def add(self, text: str, embedding: np.ndarray, response: str):
        self.texts.append(text)
        self.embeddings.append(embedding)
        self.responses.append(response)
```

## Streaming Responses

### Async Streaming Handler

```python
import asyncio
from typing import AsyncGenerator

async def stream_completion(
    prompt: str,
    on_token: callable = None
) -> AsyncGenerator[str, None]:
    """Stream AI completion tokens."""
    from openai import AsyncOpenAI

    client = AsyncOpenAI()
    stream = await client.chat.completions.create(
        model="gpt-4",
        messages=[{"role": "user", "content": prompt}],
        stream=True
    )

    async for chunk in stream:
        if chunk.choices[0].delta.content:
            token = chunk.choices[0].delta.content
            if on_token:
                on_token(token)
            yield token

# Usage
async def main():
    full_response = ""
    async for token in stream_completion("Explain AI integration"):
        print(token, end="", flush=True)
        full_response += token
    print()  # Newline at end
```

## Monitoring and Observability

### Request Logging

```python
import logging
import time
from functools import wraps
from typing import Callable

logger = logging.getLogger("ai_integration")

def log_api_call(func: Callable) -> Callable:
    """Decorator to log API calls with metrics."""
    @wraps(func)
    def wrapper(*args, **kwargs):
        start_time = time.time()
        request_id = str(uuid.uuid4())[:8]

        logger.info(f"[{request_id}] API call started: {func.__name__}")

        try:
            result = func(*args, **kwargs)
            duration = (time.time() - start_time) * 1000

            logger.info(
                f"[{request_id}] API call completed: "
                f"duration={duration:.2f}ms"
            )

            # Emit metrics
            emit_metric("api_call_duration", duration, tags={
                "function": func.__name__,
                "status": "success"
            })

            return result

        except Exception as e:
            duration = (time.time() - start_time) * 1000

            logger.error(
                f"[{request_id}] API call failed: "
                f"error={e}, duration={duration:.2f}ms"
            )

            emit_metric("api_call_duration", duration, tags={
                "function": func.__name__,
                "status": "error"
            })

            raise

    return wrapper
```

### Health Check Endpoint

```python
from dataclasses import dataclass
from typing import Dict

@dataclass
class HealthStatus:
    healthy: bool
    providers: Dict[str, bool]
    latency_ms: Dict[str, float]
    details: str

def check_health(providers: List[AIProvider]) -> HealthStatus:
    """Check health of all AI providers."""
    provider_status = {}
    provider_latency = {}

    for provider in providers:
        name = type(provider).__name__
        start = time.time()
        try:
            provider_status[name] = provider.health_check()
            provider_latency[name] = (time.time() - start) * 1000
        except Exception as e:
            provider_status[name] = False
            provider_latency[name] = -1

    all_healthy = all(provider_status.values())
    any_healthy = any(provider_status.values())

    return HealthStatus(
        healthy=any_healthy,
        providers=provider_status,
        latency_ms=provider_latency,
        details="All providers operational" if all_healthy
                else f"Degraded: {sum(provider_status.values())}/{len(providers)} healthy"
    )
```

## Best Practices

### Configuration Management

```python
from pydantic import BaseSettings, Field

class AIConfig(BaseSettings):
    """AI integration configuration."""

    # Provider settings
    openai_api_key: str = Field(..., env="OPENAI_API_KEY")
    anthropic_api_key: str = Field(..., env="ANTHROPIC_API_KEY")
    default_model: str = Field("gpt-4", env="AI_DEFAULT_MODEL")

    # Performance settings
    timeout_seconds: int = Field(30, env="AI_TIMEOUT")
    max_retries: int = Field(3, env="AI_MAX_RETRIES")
    rate_limit_rpm: int = Field(60, env="AI_RATE_LIMIT_RPM")

    # Caching settings
    cache_ttl_seconds: int = Field(3600, env="AI_CACHE_TTL")
    enable_caching: bool = Field(True, env="AI_ENABLE_CACHE")

    class Config:
        env_file = ".env"
        env_file_encoding = "utf-8"
```

### Security Guidelines

1. **Never hardcode API keys** - Use environment variables or secrets managers
2. **Rotate keys regularly** - Implement 90-day key rotation
3. **Use least privilege** - Grant minimal required permissions
4. **Encrypt in transit** - Always use HTTPS/TLS 1.3
5. **Audit API usage** - Log all requests for security review
6. **Validate inputs** - Sanitize prompts to prevent injection
7. **Handle errors securely** - Don't expose internal details in errors

### Performance Optimization

1. **Batch requests** - Combine multiple prompts when possible
2. **Cache responses** - Cache deterministic queries (temperature=0)
3. **Use streaming** - Stream long responses for better UX
4. **Optimize prompts** - Shorter prompts = faster responses + lower cost
5. **Choose right model** - Use smaller models for simple tasks
6. **Connection pooling** - Reuse HTTP connections
7. **Async processing** - Use async for concurrent requests

## Quality Assurance

Before production deployment:

- [ ] All API keys stored in secrets manager
- [ ] Error handling tested for all failure modes
- [ ] Rate limiting configured and tested
- [ ] Retry logic implemented with backoff
- [ ] Circuit breaker configured for cascading failure prevention
- [ ] Health checks implemented and monitored
- [ ] Logging and metrics collection enabled
- [ ] Caching strategy implemented where appropriate
- [ ] Multi-provider failover tested
- [ ] Load testing completed for expected traffic
