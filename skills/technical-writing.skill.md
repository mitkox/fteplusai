---
skill: 'technical-writing'
version: '2.0.0'
updated: '2025-12-31'
category: 'documentation'
complexity: 'foundational'
prerequisite_skills: []
composable_with: ['document-structure', 'ai-terminology', 'code-examples']
---

# Technical Writing Skill

## Overview
This skill ensures clear, concise, and effective technical communication for R&D audiences with varying levels of AI expertise. It establishes standards for writing quality, style consistency, and audience-appropriate content that enables successful AI adoption.

## Core Principles

### 1. Clarity Over Cleverness
- Use simple, direct language that serves the reader
- Avoid jargon unless necessary (and define it when used)
- One main idea per sentence
- Active voice over passive voice
- Write for understanding, not for impression

### 2. Reader-Centric Writing
- Start with what the reader needs
- Provide context before details
- Answer "why" before "how"
- Respect the reader's time

### 3. Precision and Accuracy
- Every technical claim must be verifiable
- Version numbers, commands, and code must be tested
- Statistics must cite sources
- Avoid vague quantifiers

## Writing Style Guidelines

### Voice and Tone

**Use Active Voice:**
| Passive (Avoid) | Active (Prefer) |
|-----------------|-----------------|
| The configuration file should be edited | Edit the configuration file |
| Data is processed by the system | The system processes data |
| The button should be clicked | Click the button |
| Errors are logged by the application | The application logs errors |

**When Passive Voice is Acceptable:**
- Emphasizing the action recipient: "The model was trained on 1M examples"
- Unknown actor: "The configuration was changed yesterday"
- Scientific/formal contexts: "The experiment was conducted"

**Tone by Context:**

| Context | Tone | Example |
|---------|------|---------|
| Tutorials | Encouraging, supportive | "You're making great progress! Now let's..." |
| Reference | Neutral, precise | "The parameter accepts integer values 1-100" |
| Troubleshooting | Calm, reassuring | "This error is common and easy to fix" |
| Executive | Confident, concise | "We recommend Option A based on ROI analysis" |

### Sentence Structure

**Length Guidelines:**
- **Average:** 15-20 words per sentence
- **Maximum:** 30 words (rare exceptions)
- **Variety:** Mix short (8-12) and medium (15-25) sentences

**Structure Patterns:**

**Simple (subject-verb-object):**
```
The API returns a JSON response.
```

**Compound (idea + idea):**
```
The API returns a JSON response, and errors include descriptive messages.
```

**Complex (main + dependent clause):**
```
When the request succeeds, the API returns a JSON response.
```

**Avoid Nested Clauses:**

| Complex (Avoid) | Simple (Prefer) |
|-----------------|-----------------|
| "The AI agent, which was developed to automate code reviews, can be configured by users who have administrator privileges to examine pull requests that meet specific criteria defined in the settings." | "The AI agent automates code reviews. Administrators can configure it to examine pull requests. The agent uses criteria defined in the settings." |

### Paragraph Structure

**Guidelines:**
- 3-5 sentences per paragraph
- One main idea per paragraph
- Topic sentence first
- Supporting details follow
- Transitional phrases between paragraphs

**Paragraph Template:**
```
[Topic sentence - main point]
[Supporting detail 1]
[Supporting detail 2]
[Example or evidence]
[Concluding/transitional sentence]
```

### Word Choice

**Prefer Simple Words:**

| Instead of... | Use... |
|---------------|--------|
| Utilize | Use |
| Facilitate | Help, Enable |
| Implement | Build, Create, Set up |
| Leverage | Use |
| Optimize | Improve |
| Commence | Start, Begin |
| Terminate | Stop, End |
| Subsequent | Next, Later |
| Prior to | Before |
| In order to | To |

**Eliminate Filler Phrases:**

| Remove | Keep |
|--------|------|
| "In order to configure..." | "To configure..." |
| "Due to the fact that..." | "Because..." |
| "At this point in time..." | "Now..." |
| "In the event that..." | "If..." |
| "It should be noted that..." | [Just state it] |
| "As a matter of fact..." | [Just state it] |
| "For all intents and purposes..." | "Effectively..." or remove |

**Be Specific:**

| Vague | Specific |
|-------|----------|
| "Significantly faster" | "40% faster" |
| "Recently updated" | "Updated December 2025" |
| "Various options" | "Three options" |
| "Large dataset" | "1 million records" |
| "Improved performance" | "Reduced latency from 200ms to 50ms" |

### Formatting Conventions

**Emphasis:**
- **Bold** for key terms on first use
- **Bold** for UI elements: "Click **Save**"
- *Italics* for emphasis within text
- `Code formatting` for commands, file names, code
- "Quotes" for user input or exact text

**Lists:**

Use **numbered lists** for:
- Sequential steps
- Prioritized items
- Items that need reference ("See step 3")

Use **bullet lists** for:
- Unordered collections
- Features or benefits
- Related items without sequence

**List Formatting:**
- Parallel structure across items
- Consistent punctuation
- Complete sentences or consistent fragments

| Inconsistent | Consistent |
|--------------|------------|
| • Installing the package | • Install the package |
| • You should configure settings | • Configure the settings |
| • Test the integration | • Test the integration |

## Audience Adaptation

### Audience Profiles

**Executive/C-Suite:**
- Focus: Business value, ROI, strategic impact
- Detail level: High-level summaries
- Jargon: Minimal, define if necessary
- Length: 1-2 pages maximum
- Structure: Executive summary first, details in appendix

**R&D Managers:**
- Focus: Resource requirements, timelines, risks
- Detail level: Moderate with ability to drill down
- Jargon: Industry-standard terms acceptable
- Length: 3-10 pages typical
- Structure: Summary → Details → Recommendations

**Technical Leads/Architects:**
- Focus: Design decisions, trade-offs, integration
- Detail level: Comprehensive with rationale
- Jargon: Technical terms expected
- Length: Variable, depth over brevity
- Structure: Problem → Options → Recommendation → Implementation

**Developers:**
- Focus: How to implement, code examples, troubleshooting
- Detail level: Step-by-step with verification
- Jargon: Technical terms expected and preferred
- Length: As needed for completeness
- Structure: Quick start → Full guide → Reference

**End Users:**
- Focus: How to accomplish tasks
- Detail level: Minimal theory, maximum practice
- Jargon: Avoid; use familiar terms
- Length: Shortest path to success
- Structure: Goal → Steps → Verification

### Audience-Specific Writing

**For Executives:**
```markdown
## Executive Summary

**Recommendation:** Replace offshore QA vendor with AI-powered testing.

**Investment:** $45,000 (Year 1)
**Annual Savings:** $180,000
**Payback Period:** 3 months
**3-Year ROI:** 850%

**Key Benefits:**
- 60% cost reduction
- 4x faster test execution
- Improved quality metrics
```

**For Developers:**
```markdown
## Quick Start

Install the CLI:
```bash
npm install -g @company/ai-tools
```

Authenticate:
```bash
ai-tools auth login
```

Run your first analysis:
```bash
ai-tools analyze ./src --output report.json
```
```

## Writing Patterns

### Pattern 1: Explaining Concepts

**Structure:** Define → Relate → Show → Apply

```markdown
## What is [Concept]?

**[Concept]** is [clear definition in one sentence].

### How It Relates to [Familiar Concept]
[Connection to something the reader knows]

### Example
[Concrete example showing the concept]

### When to Use [Concept]
[Practical application guidance]
```

### Pattern 2: Giving Instructions

**Structure:** Goal → Prerequisites → Steps → Verification

```markdown
## [Task Name]

**Goal:** [What the reader will accomplish]

### Prerequisites
- [Required item 1]
- [Required item 2]

### Steps

1. **[Action verb] [object]**
   [Details if needed]
   
2. **[Action verb] [object]**
   [Details if needed]

### Verify Success
[How to confirm the task is complete]
```

### Pattern 3: Comparing Options

**Structure:** Context → Criteria → Options → Recommendation

```markdown
## Comparing [Options]

### Context
[Why this comparison matters]

### Evaluation Criteria
| Criterion | Weight | Description |
|-----------|--------|-------------|
| [Criterion 1] | [%] | [What it means] |

### Options Summary
| Option | [Criterion 1] | [Criterion 2] | Overall |
|--------|---------------|---------------|---------|
| [A] | [Rating] | [Rating] | [Score] |
| [B] | [Rating] | [Rating] | [Score] |

### Recommendation
[Clear recommendation with rationale]
```

### Pattern 4: Troubleshooting

**Structure:** Symptom → Cause → Solution → Prevention

```markdown
## [Problem Name]

### Symptoms
- [What the user observes]
- [Error messages]

### Cause
[Why this happens]

### Solution
1. [Step to fix]
2. [Step to verify]

### Prevention
[How to avoid in the future]
```

## Code in Documentation

### Code Example Standards

**Requirements:**
- All code examples must be tested and working
- Include language identifier for syntax highlighting
- Show expected output when helpful
- Include error handling for production code
- Comment non-obvious lines

**Good Code Example:**
```python
# Configure the AI client with retry logic
from openai import OpenAI
import os

client = OpenAI(
    api_key=os.environ["OPENAI_API_KEY"],  # Never hardcode keys
    timeout=30.0,
    max_retries=3
)

# Make a completion request
response = client.chat.completions.create(
    model="gpt-4",
    messages=[{"role": "user", "content": "Hello!"}]
)

print(response.choices[0].message.content)
# Output: Hello! How can I help you today?
```

### Command Examples

**Format:**
```bash
# Description of what this command does
command --flag value
```

**With Output:**
```bash
$ ai-tools --version
ai-tools v2.3.1

$ ai-tools status
Status: Connected
Model: gpt-4
Usage: 1,234 tokens today
```

## Quality Checklist

### Pre-Writing
- [ ] Audience clearly identified
- [ ] Purpose/goal defined
- [ ] Key messages determined
- [ ] Outline/structure planned

### During Writing
- [ ] Active voice used (>80%)
- [ ] Sentences average 15-20 words
- [ ] Jargon defined on first use
- [ ] Examples provided for concepts
- [ ] Code tested and working

### Post-Writing
- [ ] Read aloud for flow
- [ ] Consistent terminology throughout
- [ ] All links verified
- [ ] Code examples tested
- [ ] Spelling/grammar checked
- [ ] Audience review completed

## Common Mistakes to Avoid

### Mistake 1: Assuming Knowledge
**Problem:** Jumping into details without context
**Solution:** Brief context before diving in

### Mistake 2: Wall of Text
**Problem:** Long paragraphs without breaks
**Solution:** Break up with headings, lists, code blocks

### Mistake 3: Passive Voice Overuse
**Problem:** "The file should be saved by the user"
**Solution:** "Save the file"

### Mistake 4: Vague Instructions
**Problem:** "Configure the settings appropriately"
**Solution:** "Set `timeout` to 30 seconds and `retries` to 3"

### Mistake 5: Missing Verification
**Problem:** Steps without confirmation of success
**Solution:** Include "Verify: You should see..."

## Evaluation Criteria

| Criterion | Poor | Acceptable | Excellent |
|-----------|------|------------|-----------|
| **Clarity** | Confusing, ambiguous | Understandable | Crystal clear |
| **Conciseness** | Wordy, redundant | Reasonable length | Efficiently written |
| **Accuracy** | Errors present | Mostly correct | 100% accurate |
| **Completeness** | Missing info | Adequate | Comprehensive |
| **Audience Fit** | Wrong level | Somewhat appropriate | Perfect match |

## Success Metrics

### Readability
- **Flesch Reading Ease:** 60-70 (standard technical)
- **Grade Level:** 10-12 (accessible professional)
- **Passive Voice:** <20% of sentences

### Effectiveness
- **Task Success:** Users complete tasks without help
- **Comprehension:** Single-read understanding
- **Findability:** Information located quickly

### Quality
- **Accuracy:** Zero technical errors
- **Currency:** Updated within 30 days of changes
- **Consistency:** Uniform style throughout

## Tools and Resources

### Readability Analysis
- Hemingway Editor (hemingwayapp.com)
- Readable.com
- Microsoft Word readability statistics

### Grammar and Style
- Grammarly
- Vale (programmable linter)
- LanguageTool

### Documentation Linters
- markdownlint
- write-good
- alex (inclusive language)

## Related Skills

- **#document-structure** - Organizing content hierarchies
- **#ai-terminology** - Consistent AI/ML vocabulary
- **#code-examples** - Technical code documentation
- **#data-visualization** - Visual communication
