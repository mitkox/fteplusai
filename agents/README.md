# FTE+AI Agent Registry

> Machine-readable registry of all specialized agents in the FTE+AI Program Framework

## Registry Metadata

```yaml
registry:
  name: FTE+AI Agent Registry
  version: 2.0.0
  updated: 2025-12-31
  total_agents: 18
  framework_version: 4.0.0
```

## Agent Index

### Quick Reference

| Agent | Category | Phase | Primary Purpose |
|-------|----------|-------|-----------------|
| [Program-Manager](#program-manager-agent) | Orchestration | All | Program execution and governance |
| [Executive-Strategy-Advisor](#executive-strategy-advisor-agent) | Strategic | 1 | C-suite strategy and presentations |
| [Documaster](#documaster-agent) | Documentation | All | Technical documentation |
| [ROI-Calculator](#roi-calculator-agent) | Financial | 1-2 | Financial analysis and ROI |
| [Tool-Evaluation-Specialist](#tool-evaluation-specialist-agent) | Evaluation | 1 | AI tool selection |
| [Security-Risk-Compliance-Advisor](#security-risk-compliance-advisor-agent) | Compliance | 1-3 | Security and compliance |
| [Legal-Contract-Advisor](#legal-contract-advisor-agent) | Legal | 1,3 | Contract and legal review |
| [Implementation-Guide](#implementation-guide-agent) | Implementation | 2 | Setup tutorials |
| [Performance-Optimization-Agent](#performance-optimization-agent) | Operations | 2-3 | Performance metrics |
| [Change-Management-Coach](#change-management-coach-agent) | People | 2-3 | Training and adoption |
| [Vendor-Transition-Manager](#vendor-transition-manager-agent) | Transition | 2-3 | Vendor wind-down |
| [Case-Study-Documenter](#case-study-documenter-agent) | Documentation | 3 | Success stories |
| [API-Integration-Specialist](#api-integration-specialist-agent) | Technical | 2 | API integration |
| [Local-AI-Infrastructure-Architect](#local-ai-infrastructure-architect-agent) | Infrastructure | 1-2 | Local AI design |
| [Open-Source-Model-Evaluator](#open-source-model-evaluator-agent) | Evaluation | 1 | Model selection |
| [Data-Sovereignty-Advisor](#data-sovereignty-advisor-agent) | Compliance | 1-3 | Data compliance |
| [Vendor-Relationship-Manager](#vendor-relationship-manager-agent) | Vendor | 1-3 | Vendor negotiations |
| [MLOps-Engineer](#mlops-engineer-agent) | Operations | 3 | Production operations |

---

## Agents by Program Phase

### Phase 1: Planning & Preparation (Days 1-30)

```yaml
phase_1_agents:
  primary:
    - Program-Manager           # Program orchestration
    - Executive-Strategy-Advisor # Business case, board presentations
    - ROI-Calculator            # Financial justification
    - Tool-Evaluation-Specialist # AI tool selection
  
  supporting:
    - Security-Risk-Compliance-Advisor # Security assessment
    - Legal-Contract-Advisor    # Contract review
    - Documaster               # Program documentation
    - Local-AI-Infrastructure-Architect # If self-hosted
    - Open-Source-Model-Evaluator # If open source models
    - Data-Sovereignty-Advisor  # If data sovereignty required
```

### Phase 2: Pilot & Validation (Days 31-60)

```yaml
phase_2_agents:
  primary:
    - Program-Manager           # Continue orchestration
    - Implementation-Guide      # Tool deployment
    - Change-Management-Coach   # Training delivery
    - Performance-Optimization-Agent # Metrics tracking
  
  supporting:
    - Vendor-Transition-Manager # Parallel run coordination
    - API-Integration-Specialist # Technical integration
    - Documaster               # Pilot documentation
    - ROI-Calculator           # ROI validation
```

### Phase 3: Transition & Scale (Days 61-90)

```yaml
phase_3_agents:
  primary:
    - Program-Manager           # Program closure
    - Vendor-Transition-Manager # Vendor wind-down
    - Change-Management-Coach   # Full rollout
    - MLOps-Engineer           # Production operations
  
  supporting:
    - Case-Study-Documenter    # Success documentation
    - Security-Risk-Compliance-Advisor # Production readiness
    - Documaster               # Final documentation
    - ROI-Calculator           # Final ROI validation
```

---

## Detailed Agent Registry

### Program-Manager Agent

```yaml
agent:
  name: Program-Manager
  file: Program-Manager.agent.md
  version: 1.0.0
  category: orchestration
  
  description: |
    Orchestrates complete vendor replacement programs from planning 
    through execution, providing program governance, milestone tracking, 
    risk management, and stakeholder coordination.
  
  tools:
    - ReadFile
    - WriteFile
    - StrReplaceFile
    - Glob
  
  skills:
    - program-planning
    - milestone-tracking
    - risk-assessment
    - stakeholder-management
  
  orchestration:
    pattern: orchestrator-workers
    coordinates:
      - all-agents
    reports_to:
      - executive-sponsor
  
  use_cases:
    - Starting new vendor replacement programs
    - Creating 90-day execution roadmaps
    - Weekly/monthly status reporting
    - Phase gate assessments
    - Risk escalation
```

### Executive-Strategy-Advisor Agent

```yaml
agent:
  name: Executive-Strategy-Advisor
  file: Executive-Strategy-Advisor.agent.md
  version: 1.0.0
  category: strategic
  
  description: |
    Strategic advisor for C-suite and board-level decision making,
    creating executive summaries, strategic roadmaps, and business cases.
  
  tools:
    - ReadFile
    - WriteFile
    - SearchWeb
    - FetchURL
  
  skills:
    - financial-modeling
    - data-visualization
    - document-structure
    - technical-writing
  
  orchestration:
    pattern: specialist
    receives_from:
      - ROI-Calculator
      - Program-Manager
    provides_to:
      - Documaster
      - Program-Manager
```

### Documaster Agent

```yaml
agent:
  name: Documaster
  file: Documaster.agent.md
  version: 2.0.0
  category: documentation
  
  description: |
    Primary documentation agent creating and maintaining all program
    documentation from executive summaries to technical specifications.
  
  tools:
    - ReadFile
    - WriteFile
    - StrReplaceFile
    - Glob
    - Shell
    - SearchWeb
    - FetchURL
  
  skills:
    - document-structure
    - technical-writing
    - ai-terminology
    - code-examples
  
  orchestration:
    pattern: hub-and-spoke
    receives_from:
      - all-agents
    provides_to:
      - stakeholders
      - other-agents
```

### ROI-Calculator Agent

```yaml
agent:
  name: ROI-Calculator
  file: ROI-Calculator.agent.md
  version: 2.0.0
  category: financial
  
  description: |
    Financial analysis specialist creating cost-benefit analyses,
    ROI models, and tracking savings vs. projections.
  
  tools:
    - ReadFile
    - WriteFile
    - Shell
    - SearchWeb
    - FetchURL
  
  skills:
    - financial-modeling
    - data-visualization
    - document-structure
    - technical-writing
  
  orchestration:
    pattern: specialist
    receives_from:
      - Performance-Optimization-Agent
      - Vendor-Transition-Manager
      - Tool-Evaluation-Specialist
    provides_to:
      - Executive-Strategy-Advisor
      - Program-Manager
      - Documaster
```

### Tool-Evaluation-Specialist Agent

```yaml
agent:
  name: Tool-Evaluation-Specialist
  file: Tool-Evaluation-Specialist.agent.md
  version: 1.0.0
  category: evaluation
  
  description: |
    Tool selection specialist providing objective AI vendor evaluation
    with scorecards, POC frameworks, and build vs. buy analysis.
  
  tools:
    - ReadFile
    - WriteFile
    - SearchWeb
    - FetchURL
  
  skills:
    - tool-evaluation
    - technical-writing
    - data-visualization
    - code-examples
    - financial-modeling
```

### Security-Risk-Compliance-Advisor Agent

```yaml
agent:
  name: Security-Risk-Compliance-Advisor
  file: Security-Risk-Compliance-Advisor.agent.md
  version: 1.0.0
  category: compliance
  
  description: |
    Comprehensive security, risk, and compliance specialist for
    enterprise AI adoption including GDPR, SOC2, HIPAA requirements.
  
  tools:
    - ReadFile
    - WriteFile
    - StrReplaceFile
    - SearchWeb
    - FetchURL
  
  skills:
    - risk-assessment
    - legal-compliance
    - document-structure
    - technical-writing
```

### Implementation-Guide Agent

```yaml
agent:
  name: Implementation-Guide
  file: Implementation-Guide.agent.md
  version: 2.0.0
  category: implementation
  
  description: |
    Creates practical, actionable implementation guides including
    step-by-step tutorials, onboarding, and troubleshooting.
  
  tools:
    - ReadFile
    - WriteFile
    - StrReplaceFile
    - Shell
    - Glob
  
  skills:
    - document-structure
    - technical-writing
    - code-examples
    - ai-terminology
  
  orchestration:
    pattern: pipeline
    receives_from:
      - Tool-Evaluation-Specialist
      - Local-AI-Infrastructure-Architect
    provides_to:
      - Change-Management-Coach
      - MLOps-Engineer
```

### MLOps-Engineer Agent

```yaml
agent:
  name: MLOps-Engineer
  file: MLOps-Engineer.agent.md
  version: 1.0.0
  category: operations
  
  description: |
    Operations specialist for running production local AI infrastructure
    with monitoring, incident response, and capacity management.
  
  tools:
    - ReadFile
    - WriteFile
    - StrReplaceFile
    - Glob
    - Shell
    - Grep
  
  skills:
    - mlops-operations
    - local-ai-deployment
    - production-readiness
    - metrics-analytics
```

---

## Orchestration Patterns

### Pattern Reference

| Pattern | Description | Example Agents |
|---------|-------------|----------------|
| **Orchestrator-Workers** | Central coordinator delegates to specialists | Program-Manager |
| **Hub-and-Spoke** | Central hub receives and synthesizes from many | Documaster |
| **Pipeline** | Sequential processing through specialists | Implementation-Guide |
| **Specialist** | Deep expertise in narrow domain | ROI-Calculator |
| **Evaluator-Optimizer** | Generate then critique loop | Tool-Evaluation-Specialist |

### Agent Interaction Matrix

```
                    PM   ESA  Doc  ROI  TES  SRC  LCA  IG   POA  CMC  VTM  CSD  API  LAI  OSE  DSA  VRM  MLO
Program-Manager     ●    ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→   ←→
Exec-Strategy       ←→   ●    →    ←    ←          ←                                                    
Documaster          ←→   ←    ●    ←    ←    ←    ←    ←    ←    ←    ←    ←    ←    ←    ←    ←    ←    ←
ROI-Calculator      ←→   →    →    ●         ←    ←         ←         ←              ←    
Tool-Eval-Spec      ←→        →    →    ●                   →                        →    →         
Security-Risk       ←→        →    →         ●                        ←                   ←    ←    
Legal-Contract      ←→        →    →              ●                        ←                   ←    
Implementation      ←→        →              ←    ←    ●              →              →    ←         →
Perf-Optimization   ←→        →    →              ←         ●              →                             
Change-Management   ←→        →    ←                   ←    ←    ●    ←                                  
Vendor-Transition   ←→        →    ←    ←    ←    ←    ←         ←    ●         ←                   ←    
Case-Study-Doc      ←→        →    ←                             ←         ●                             
API-Integration     ←→        →                        ←              ←              ●                   
Local-AI-Infra      ←→        →    →    ←    ←              →                             ●    ←    ←    →
Open-Source-Model   ←→        →         ←                                                  ←    ●    ←    
Data-Sovereignty    ←→        →         ←    ←    ←                                       ←    ←    ●    
Vendor-Relationship ←→        →    ←         ←    ←                   ←                                  ●
MLOps-Engineer      ←→        →              ←    ←    ←         ←         ←              ←              ●

Legend: ● = Self  ← = Receives from  → = Provides to  ←→ = Bidirectional
```

---

## Usage Guidelines

### Selecting the Right Agent

1. **Identify the task category** (strategic, technical, operational)
2. **Determine the program phase** (planning, pilot, transition)
3. **Check the agent's primary use cases**
4. **Verify required tools are available**
5. **Consider orchestration dependencies**

### Multi-Agent Workflows

```yaml
# Example: Creating a business case
workflow:
  name: Business Case Creation
  steps:
    - agent: ROI-Calculator
      task: Create financial model
      output: financial_model.md
      
    - agent: Tool-Evaluation-Specialist
      task: Compare tool options
      output: tool_comparison.md
      
    - agent: Security-Risk-Compliance-Advisor
      task: Risk assessment
      output: risk_assessment.md
      
    - agent: Executive-Strategy-Advisor
      task: Compile business case
      inputs:
        - financial_model.md
        - tool_comparison.md
        - risk_assessment.md
      output: business_case.md
      
    - agent: Documaster
      task: Format for presentation
      output: business_case_final.md
```

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 2.0.0 | 2025-12-31 | Added orchestration patterns, YAML metadata, interaction matrix |
| 1.0.0 | 2025-12-21 | Initial registry |
