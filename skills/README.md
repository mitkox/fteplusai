# FTE+AI Skills Registry

> Machine-readable registry of all reusable expertise modules in the FTE+AI Program Framework

## Registry Metadata

```yaml
registry:
  name: FTE+AI Skills Registry
  version: 2.0.0
  updated: 2025-12-31
  total_skills: 23
  framework_version: 4.0.0
```

## Skills Index

### Quick Reference by Category

| Category | Skills | Primary Use |
|----------|--------|-------------|
| **Documentation** | document-structure, technical-writing, ai-terminology, code-examples | Creating clear documentation |
| **Financial** | financial-modeling, data-visualization, metrics-analytics | ROI and cost analysis |
| **Program Management** | program-planning, milestone-tracking, stakeholder-management | Program execution |
| **Compliance & Risk** | risk-assessment, legal-compliance, data-sovereignty | Compliance and risk management |
| **Technical** | api-integration, code-examples, production-readiness | Technical implementation |
| **Change & Transition** | change-management, vendor-transition, vendor-negotiation | Organizational change |
| **Infrastructure** | local-ai-deployment, hardware-sizing, mlops-operations | AI infrastructure |
| **Evaluation** | tool-evaluation, open-source-licensing | Tool and model selection |

---

## Skills by Complexity Level

### Foundational Skills
*No prerequisites - core building blocks*

```yaml
foundational:
  - skill: document-structure
    description: Organizing documentation hierarchies
    
  - skill: technical-writing
    description: Clear technical communication
    
  - skill: ai-terminology
    description: Consistent AI/ML vocabulary
    
  - skill: code-examples
    description: Working code samples and patterns
```

### Intermediate Skills
*Build on foundational skills*

```yaml
intermediate:
  - skill: program-planning
    prerequisites: [document-structure]
    
  - skill: milestone-tracking
    prerequisites: [document-structure, program-planning]
    
  - skill: stakeholder-management
    prerequisites: [document-structure, technical-writing]
    
  - skill: financial-modeling
    prerequisites: [data-visualization]
    
  - skill: risk-assessment
    prerequisites: [document-structure]
    
  - skill: change-management
    prerequisites: [stakeholder-management]
    
  - skill: tool-evaluation
    prerequisites: [document-structure, data-visualization]
    
  - skill: api-integration
    prerequisites: [code-examples]
```

### Advanced Skills
*Require multiple intermediate skills*

```yaml
advanced:
  - skill: vendor-transition
    prerequisites: [program-planning, risk-assessment, change-management]
    
  - skill: local-ai-deployment
    prerequisites: [hardware-sizing, code-examples]
    
  - skill: mlops-operations
    prerequisites: [local-ai-deployment, production-readiness, metrics-analytics]
    
  - skill: data-sovereignty
    prerequisites: [risk-assessment, legal-compliance]
```

---

## Detailed Skills Registry

### Documentation Skills

#### document-structure
```yaml
skill:
  name: document-structure
  file: document-structure.skill.md
  version: 2.0.0
  category: documentation
  complexity: foundational
  
  description: |
    Expertise in organizing complex technical documentation with 
    clear hierarchies, logical flow, and intuitive navigation.
  
  key_capabilities:
    - Information architecture and hierarchy
    - Document type selection and templates
    - Navigation design
    - Structural patterns for different purposes
  
  composable_with:
    - technical-writing
    - data-visualization
    - ai-terminology
  
  used_by_agents:
    - Documaster
    - Program-Manager
    - Executive-Strategy-Advisor
```

#### technical-writing
```yaml
skill:
  name: technical-writing
  file: technical-writing.skill.md
  version: 2.0.0
  category: documentation
  complexity: foundational
  
  description: |
    Clear, concise, and effective technical communication for 
    R&D audiences with varying levels of AI expertise.
  
  key_capabilities:
    - Writing style and voice guidelines
    - Audience adaptation
    - Readability optimization
    - Quality checklists
  
  composable_with:
    - document-structure
    - ai-terminology
    - code-examples
  
  used_by_agents:
    - Documaster
    - Implementation-Guide
    - Case-Study-Documenter
```

#### ai-terminology
```yaml
skill:
  name: ai-terminology
  file: ai-terminology.skill.md
  version: 1.0.0
  category: documentation
  complexity: foundational
  
  description: |
    Consistent AI/ML terminology and definitions for clear 
    communication across technical and business audiences.
  
  key_capabilities:
    - Standard AI/ML terms glossary
    - Vendor-neutral language
    - Audience-appropriate explanations
    - Term translation between audiences
  
  composable_with:
    - technical-writing
    - document-structure
```

#### code-examples
```yaml
skill:
  name: code-examples
  file: code-examples.skill.md
  version: 1.0.0
  category: documentation
  complexity: foundational
  
  description: |
    Working code samples, integration patterns, and 
    security-conscious coding guidelines.
  
  key_capabilities:
    - Production-quality code samples
    - Multi-language support (Python, TypeScript, Bash)
    - Security best practices
    - Error handling patterns
  
  composable_with:
    - technical-writing
    - api-integration
```

### Financial Skills

#### financial-modeling
```yaml
skill:
  name: financial-modeling
  file: financial-modeling.skill.md
  version: 1.0.0
  category: financial
  complexity: intermediate
  
  description: |
    ROI calculations, TCO analysis, cost models, and 
    financial justification for AI investments.
  
  key_capabilities:
    - ROI calculation frameworks
    - Total cost of ownership models
    - Cost-benefit analysis
    - Sensitivity analysis
    - Payback period calculation
  
  composable_with:
    - data-visualization
    - risk-assessment
  
  used_by_agents:
    - ROI-Calculator
    - Executive-Strategy-Advisor
```

#### data-visualization
```yaml
skill:
  name: data-visualization
  file: data-visualization.skill.md
  version: 1.0.0
  category: financial
  complexity: foundational
  
  description: |
    Charts, tables, dashboards, and metrics presentation 
    for technical and executive audiences.
  
  key_capabilities:
    - Chart selection guidance
    - Dashboard design
    - Metrics visualization
    - Executive summary graphics
  
  composable_with:
    - financial-modeling
    - metrics-analytics
    - document-structure
```

#### metrics-analytics
```yaml
skill:
  name: metrics-analytics
  file: metrics-analytics.skill.md
  version: 1.0.0
  category: financial
  complexity: intermediate
  
  description: |
    Productivity measurement, ROI validation, and 
    continuous improvement tracking.
  
  key_capabilities:
    - Productivity metrics frameworks
    - Baseline measurement
    - Performance tracking
    - Dashboard design
  
  composable_with:
    - data-visualization
    - financial-modeling
  
  used_by_agents:
    - Performance-Optimization-Agent
    - ROI-Calculator
```

### Program Management Skills

#### program-planning
```yaml
skill:
  name: program-planning
  file: program-planning.skill.md
  version: 1.0.0
  category: program-management
  complexity: intermediate
  
  description: |
    Creating and executing 30-60-90 day vendor replacement 
    programs with governance and phase gates.
  
  key_capabilities:
    - 30-60-90 day planning frameworks
    - Milestone and dependency management
    - Resource allocation
    - Phase gate governance
  
  composable_with:
    - milestone-tracking
    - stakeholder-management
    - risk-assessment
  
  used_by_agents:
    - Program-Manager
```

#### milestone-tracking
```yaml
skill:
  name: milestone-tracking
  file: milestone-tracking.skill.md
  version: 2.0.0
  category: program-management
  complexity: intermediate
  
  description: |
    Tracking program milestones, deliverables, and dependencies 
    with status reporting and early warning.
  
  key_capabilities:
    - Status tracking and reporting
    - Dependency management
    - Deliverable tracking
    - Dashboard visualization
  
  composable_with:
    - program-planning
    - stakeholder-management
```

#### stakeholder-management
```yaml
skill:
  name: stakeholder-management
  file: stakeholder-management.skill.md
  version: 2.0.0
  category: program-management
  complexity: intermediate
  
  description: |
    Identifying, analyzing, and engaging stakeholders 
    to ensure alignment and program success.
  
  key_capabilities:
    - Stakeholder analysis frameworks
    - Power-interest matrix
    - Communication planning
    - Resistance management
  
  composable_with:
    - change-management
    - program-planning
```

### Compliance & Risk Skills

#### risk-assessment
```yaml
skill:
  name: risk-assessment
  file: risk-assessment.skill.md
  version: 1.0.0
  category: compliance
  complexity: intermediate
  
  description: |
    Security, compliance, and business risk identification, 
    analysis, and mitigation planning.
  
  key_capabilities:
    - Risk identification frameworks
    - Security assessment
    - Compliance mapping
    - Mitigation planning
  
  composable_with:
    - legal-compliance
    - program-planning
  
  used_by_agents:
    - Security-Risk-Compliance-Advisor
    - Program-Manager
```

#### legal-compliance
```yaml
skill:
  name: legal-compliance
  file: legal-compliance.skill.md
  version: 1.0.0
  category: compliance
  complexity: intermediate
  
  description: |
    Contract law, IP protection, data processing agreements, 
    and vendor contract management.
  
  key_capabilities:
    - Contract review guidelines
    - IP protection strategies
    - DPA requirements
    - Vendor exit terms
  
  composable_with:
    - risk-assessment
    - vendor-transition
  
  used_by_agents:
    - Legal-Contract-Advisor
    - Security-Risk-Compliance-Advisor
```

#### data-sovereignty
```yaml
skill:
  name: data-sovereignty
  file: data-sovereignty.skill.md
  version: 1.0.0
  category: compliance
  complexity: advanced
  
  description: |
    Data residency, privacy, and regulatory compliance 
    for AI systems (GDPR, HIPAA, CCPA).
  
  key_capabilities:
    - Data classification frameworks
    - Compliance checklists
    - PII detection strategies
    - Privacy-preserving architecture
  
  prerequisites:
    - risk-assessment
    - legal-compliance
  
  used_by_agents:
    - Data-Sovereignty-Advisor
```

### Change & Transition Skills

#### change-management
```yaml
skill:
  name: change-management
  file: change-management.skill.md
  version: 1.0.0
  category: change
  complexity: intermediate
  
  description: |
    Adoption strategies, training programs, and stakeholder 
    engagement for organizational change.
  
  key_capabilities:
    - ADKAR and Kotter frameworks
    - Training program design
    - Adoption metrics
    - Resistance management
  
  composable_with:
    - stakeholder-management
    - vendor-transition
  
  used_by_agents:
    - Change-Management-Coach
```

#### vendor-transition
```yaml
skill:
  name: vendor-transition
  file: vendor-transition.skill.md
  version: 1.0.0
  category: change
  complexity: advanced
  
  description: |
    Exit planning, knowledge transfer, parallel runs, 
    and cutover strategies for vendor replacement.
  
  key_capabilities:
    - Transition planning frameworks
    - Knowledge transfer templates
    - Parallel run procedures
    - Rollback strategies
  
  prerequisites:
    - program-planning
    - risk-assessment
    - change-management
  
  used_by_agents:
    - Vendor-Transition-Manager
```

#### vendor-negotiation
```yaml
skill:
  name: vendor-negotiation
  file: vendor-negotiation.skill.md
  version: 1.0.0
  category: change
  complexity: intermediate
  
  description: |
    Contract negotiation, pricing analysis, SLA design, 
    and multi-vendor portfolio management.
  
  key_capabilities:
    - Negotiation tactics
    - Pricing model analysis
    - Contract terms
    - Performance scorecards
  
  used_by_agents:
    - Vendor-Relationship-Manager
```

### Infrastructure Skills

#### local-ai-deployment
```yaml
skill:
  name: local-ai-deployment
  file: local-ai-deployment.skill.md
  version: 1.0.0
  category: infrastructure
  complexity: advanced
  
  description: |
    Self-hosted LLM platforms, containerized deployment, 
    and air-gapped installation.
  
  key_capabilities:
    - Platform comparison (vLLM, SGLang, LocalAI)
    - Docker/Kubernetes deployment
    - Air-gapped procedures
    - Performance optimization
  
  prerequisites:
    - hardware-sizing
    - code-examples
  
  used_by_agents:
    - Local-AI-Infrastructure-Architect
    - MLOps-Engineer
```

#### hardware-sizing
```yaml
skill:
  name: hardware-sizing
  file: hardware-sizing.skill.md
  version: 1.0.0
  category: infrastructure
  complexity: intermediate
  
  description: |
    GPU selection, server specification, capacity planning, 
    and TCO modeling for AI workloads.
  
  key_capabilities:
    - GPU selection guide
    - Server configuration templates
    - VRAM requirements
    - Capacity planning
  
  used_by_agents:
    - Local-AI-Infrastructure-Architect
```

#### mlops-operations
```yaml
skill:
  name: mlops-operations
  file: mlops-operations.skill.md
  version: 1.0.0
  category: infrastructure
  complexity: advanced
  
  description: |
    Production AI system operations including monitoring, 
    alerting, incident response, and scaling.
  
  key_capabilities:
    - Monitoring configuration
    - SLO frameworks
    - Operational runbooks
    - Capacity management
  
  prerequisites:
    - local-ai-deployment
    - production-readiness
    - metrics-analytics
  
  used_by_agents:
    - MLOps-Engineer
```

#### production-readiness
```yaml
skill:
  name: production-readiness
  file: production-readiness.skill.md
  version: 1.0.0
  category: infrastructure
  complexity: intermediate
  
  description: |
    Enterprise deployment checklists, SLAs, backup/recovery, 
    and production standards.
  
  key_capabilities:
    - Production readiness checklists
    - Deployment strategies
    - Monitoring requirements
    - Incident response procedures
  
  used_by_agents:
    - MLOps-Engineer
    - Security-Risk-Compliance-Advisor
```

### Evaluation Skills

#### tool-evaluation
```yaml
skill:
  name: tool-evaluation
  file: tool-evaluation.skill.md
  version: 1.0.0
  category: evaluation
  complexity: intermediate
  
  description: |
    Scorecards, POC frameworks, and selection criteria 
    for AI tool evaluation.
  
  key_capabilities:
    - Evaluation matrices
    - Scoring methodology
    - POC planning
    - Build vs. buy frameworks
  
  used_by_agents:
    - Tool-Evaluation-Specialist
```

#### open-source-licensing
```yaml
skill:
  name: open-source-licensing
  file: open-source-licensing.skill.md
  version: 1.0.0
  category: evaluation
  complexity: intermediate
  
  description: |
    License compliance for AI models and tools including 
    commercial use assessment and IP considerations.
  
  key_capabilities:
    - License classification
    - Commercial use eligibility
    - Compliance documentation
    - Model-specific guidance
  
  used_by_agents:
    - Open-Source-Model-Evaluator
```

#### api-integration
```yaml
skill:
  name: api-integration
  file: api-integration.skill.md
  version: 1.0.0
  category: technical
  complexity: intermediate
  
  description: |
    API/SDK integration patterns including authentication, 
    error handling, and multi-provider strategies.
  
  key_capabilities:
    - Integration patterns
    - Authentication strategies
    - Error handling
    - Rate limit management
  
  used_by_agents:
    - API-Integration-Specialist
```

---

## Skill Dependency Graph

```
                    ┌─────────────────┐
                    │ Foundational    │
                    └────────┬────────┘
                             │
    ┌────────────────────────┼────────────────────────┐
    │                        │                        │
    ▼                        ▼                        ▼
┌─────────┐           ┌─────────────┐          ┌───────────┐
│document-│           │  technical- │          │   code-   │
│structure│           │   writing   │          │ examples  │
└────┬────┘           └──────┬──────┘          └─────┬─────┘
     │                       │                       │
     │    ┌──────────────────┼───────────────┐      │
     │    │                  │               │      │
     ▼    ▼                  ▼               ▼      ▼
┌─────────────┐      ┌──────────────┐   ┌────────────────┐
│   program-  │      │ stakeholder- │   │      api-      │
│   planning  │      │  management  │   │  integration   │
└──────┬──────┘      └───────┬──────┘   └────────────────┘
       │                     │
       │    ┌────────────────┤
       ▼    ▼                ▼
┌─────────────────┐   ┌──────────────┐
│    milestone-   │   │    change-   │
│    tracking     │   │  management  │
└─────────────────┘   └───────┬──────┘
                              │
                              ▼
                    ┌─────────────────┐
                    │    vendor-      │
                    │   transition    │
                    └─────────────────┘
```

---

## Usage Guidelines

### Selecting Skills

1. **Identify the task type** (documentation, analysis, planning)
2. **Check skill prerequisites** to ensure foundation is covered
3. **Review composable skills** for enhanced capability
4. **Match to appropriate agent** for execution

### Skill Composition

Skills can be combined for complex tasks:

```yaml
# Example: Creating a business case
composition:
  primary_skill: financial-modeling
  supporting_skills:
    - document-structure  # For organization
    - data-visualization  # For charts
    - risk-assessment     # For risk section
    - technical-writing   # For clarity
```

### Skill vs. Agent Selection

| Need | Use |
|------|-----|
| Specific expertise/guidance | Skill reference |
| Complete task execution | Agent invocation |
| Template or pattern | Skill reference |
| Multi-step workflow | Agent invocation |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 2.0.0 | 2025-12-31 | Added YAML metadata, complexity levels, dependency graph |
| 1.0.0 | 2025-12-21 | Initial registry |
