# FTE+AI Program Framework - AI Agent Guide

## Project Overview

The FTE+AI Program Framework is a comprehensive 30-60-90 day program execution system designed to help R&D teams replace outsourcing vendors with AI-augmented internal teams. This is **NOT a documentation toolkit**—it is a hands-on program management framework with specialized AI agents that guide you through planning, execution, and successful cutover.

**Primary Goal:** Enable R&D organizations to reduce vendor costs by 60-80% while increasing FTE productivity by 1.5-2.5x through strategic AI augmentation—delivered in 90 days.

**Mission:** Provide complete program orchestration from initial planning through vendor cutover, with AI agents that actively guide each phase of execution.

## Technology Stack & Architecture

**System Type:** AI-Powered Program Execution Framework  
**Platform:** GitHub-based with structured agent orchestration  
**Agent Framework:** Custom chatagent format with YAML frontmatter  
**Content Format:** Markdown templates, checklists, and tracking tools  
**Version Control:** Git-based with GitHub repository structure  
**Tools Framework:** Configurable tool access for program management  
**Execution Model:** 30-60-90 day phased program delivery  
**Current Version:** 4.1.0 (Production-Ready Agent Framework)

### Core Architecture Components

1. **Agent Layer** (`agents/`): 18 specialized AI agents orchestrating program phases
2. **Skill Layer** (`skills/`): 23 reusable expertise modules for program execution  
3. **Program Framework**: 30-60-90 day structured execution model
4. **Phase Gates**: Go/No-Go decision points at Days 30, 60, 90
5. **Tracking System**: Milestone, deliverable, risk, and stakeholder management
6. **Reference Layer** (root files): Program guides and execution templates

### Modern Agent Patterns (v4.1)

This framework implements cutting-edge agent architecture patterns based on 2024-2025 best practices:

| Pattern | Description | Used By |
|---------|-------------|---------|
| **Orchestrator-Workers** | Central coordinator delegates to specialists | Program-Manager |
| **Hub-and-Spoke** | Central hub synthesizes from multiple sources | Documaster |
| **Evaluator-Optimizer** | Generate-critique-improve loops | Tool-Evaluation-Specialist |
| **Pipeline** | Sequential processing through specialists | Implementation-Guide |
| **Specialist** | Deep expertise in narrow domain | ROI-Calculator, MLOps-Engineer |

### Agent Metadata Standard (v2.0)

All agents now include enhanced YAML frontmatter:

```yaml
---
description: 'Agent purpose description'
tools: ["Tool1", "Tool2"]
version: '2.0.0'
updated: '2025-12-31'
category: 'orchestration|documentation|financial|etc'
---
```

## 🛠️ Tools Configuration

Each agent has configured tool access appropriate for their specialized functions.

### Available Tools
- **File System**: `ReadFile`, `WriteFile`, `StrReplaceFile`, `Glob` - Document manipulation
- **System Operations**: `Shell`, `Grep` - Command execution and text processing  
- **Research**: `SearchWeb`, `FetchURL` - Internet research and data gathering
- **Parallel Processing**: `Task` - Complex task decomposition and execution

### Agent Tool Access Summary
| Agent | Primary Tools | Enterprise Focus |
|-------|---------------|------------------|
| Documaster | File system + Research | Documentation creation and research |
| ROI Calculator | File + Shell + Research | Financial modeling and market analysis |
| Implementation Guide | File system + Shell | Tutorial creation with code testing |
| Case Study Documenter | File + Research | Success story creation with data |
| Vendor Transition Manager | File system + Research | Project management and planning |
| Tool Evaluation Specialist | Research focused | Market analysis and comparisons |
| Security-Risk-Compliance Advisor | File + Research | Compliance research and frameworks |
| Change Management Coach | File + Research | Training materials and surveys |
| Performance Optimization Agent | File + Shell | Data analysis and system integration |
| Executive Strategy Advisor | File + Research | Market intelligence and strategy |
| API Integration Specialist | File + Shell + Research | Technical integration guides |
| Legal Contract Advisor | File + Research | Contract analysis and compliance |
| Local AI Infrastructure Architect | File + Shell | Hardware sizing and deployment |
| Open Source Model Evaluator | File + Research | Model selection and licensing |
| Data Sovereignty Advisor | File + Research | Compliance and data protection |
| Vendor Relationship Manager | File + Research | Contract negotiation and relations |
| MLOps Engineer | File + Shell + Grep | Production operations and monitoring |

### Security Considerations
- **Principle of Least Privilege**: Agents only have tools needed for their functions
- **Audit Logging**: All tool usage is logged for security monitoring
- **Access Control**: Tool access can be restricted based on security requirements
- **Compliance Ready**: Configurations support enterprise compliance needs

## Project Structure

```
FTE+AI/
├── AGENTS.md                                 # Agent & skill reference (this file)
├── README.md                                 # Project overview
├── LICENSE                                   # MIT License
├── agents/                                   # 18 specialized program agents
├── skills/                                   # 23 reusable expertise modules
└── docs/                                     # Guides, templates, and readiness artifacts
	├── Introduction.md
	├── Enterprise-Deployment-Guide.md
	├── ROI-Calculator-Template.md
	└── production-readiness/                 # Enterprise readiness package
		├── README.md
		├── 00-Executive-Summary.md
		├── 01-Tool-Evaluation-Scorecard.md
		├── 02-POC-Plan.md
		├── 03-Risk-Assessment-Register.md
		├── 04-Security-Compliance-Checklist.md
		├── 05-Vendor-Transition-Plan.md
		├── 06-Training-Adoption-Plan.md
		├── 07-Operations-Monitoring-Plan.md
		├── 08-Incident-Response-Runbook.md
		└── 09-Go-No-Go-Signoff.md
```

## Available Agents

### Phase 1 Agents: Planning & Preparation (Days 1-30)

#### 1. Program-Manager Agent (@Program-Manager)
**Program orchestrator** for end-to-end vendor replacement execution.

**Use Cases:**
- Creating comprehensive 30-60-90 day program plans
- Tracking milestones and deliverables across all phases
- Managing phase gates and go/no-go decisions
- Coordinating all specialized agents
- Executive status reporting
- Risk escalation and mitigation

**Core Skills:** #program-planning, #milestone-tracking, #risk-assessment, #stakeholder-management

---

#### 2. Executive-Strategy-Advisor Agent (@Executive-Strategy-Advisor)
**Strategic advisor** for C-suite and board-level decision making.

**Use Cases:**
- Executive summaries and board presentations
- Strategic roadmaps for AI transformation
- Business case development for leadership
- Competitive analysis and market positioning
- Long-term AI strategy and governance frameworks

**Core Skills:** #financial-modeling, #data-visualization, #document-structure, #technical-writing

---

#### 3. Documaster Agent (@Documaster)
**Primary documentation agent** for program documentation and guides.

**Use Cases:**
- Program charter and planning documents
- Technical guides and specifications
- Executive presentations
- Reference materials
- Knowledge base content

**Core Skills:** #document-structure, #technical-writing, #ai-terminology, #code-examples

---

#### 4. ROI Calculator Agent (@ROI-Calculator)
**Financial analysis specialist** for vendor replacement business cases.

**Use Cases:**
- Cost-benefit analyses and ROI models
- Vendor vs. AI cost comparisons
- TCO calculations and payback analysis
- Budget planning and financial justification

**Core Skills:** #financial-modeling, #data-visualization, #document-structure, #technical-writing

---

#### 5. Tool Evaluation Specialist Agent (@Tool-Evaluation-Specialist)
**Tool selection specialist** for objective AI vendor evaluation.

**Use Cases:**
- Tool comparison matrices and scorecards
- Proof-of-concept evaluation frameworks
- Build vs. buy decision support
- Vendor stability and lock-in assessments

**Core Skills:** #tool-evaluation, #technical-writing, #data-visualization, #code-examples, #financial-modeling

---

#### 6. Security-Risk-Compliance-Advisor Agent (@Security-Risk-Compliance-Advisor)
**Comprehensive security, risk, and compliance specialist** for enterprise AI adoption.

**Use Cases:**
- Security architecture and data protection
- Risk assessment and mitigation frameworks
- Compliance documentation (GDPR, SOC2, HIPAA)
- Vendor security assessments

**Core Skills:** #risk-assessment, #legal-compliance, #document-structure, #technical-writing

---

#### 7. Legal-Contract-Advisor Agent (@Legal-Contract-Advisor)
**Legal and contract specialist** for AI vendor agreements and compliance.

**Use Cases:**
- AI vendor contract review and negotiation
- Intellectual property protection strategies
- Data processing agreement templates
- Vendor exit and transition contract terms

**Core Skills:** #legal-compliance, #vendor-transition, #risk-assessment, #document-structure

---

### Phase 2 Agents: Pilot & Validation (Days 31-60)

#### 8. Implementation Guide Agent (@Implementation-Guide)
**Tutorial specialist** for practical step-by-step guidance.

**Use Cases:**
- Tool onboarding and setup tutorials
- Integration guides and workflows
- Troubleshooting documentation
- Quick-start guides and training materials

**Core Skills:** #document-structure, #technical-writing, #code-examples, #ai-terminology

---

#### 9. Performance-Optimization-Agent (@Performance-Optimization-Agent)
**Performance specialist** for AI system optimization and efficiency.

**Use Cases:**
- AI tool performance benchmarking
- Cost optimization and usage efficiency
- Baseline vs. pilot metrics comparison
- Monitoring and observability setup

**Core Skills:** #metrics-analytics, #api-integration, #code-examples, #technical-writing

---

#### 10. Change Management Coach Agent (@Change-Management-Coach)
**Organizational adoption specialist** for training and rollout.

**Use Cases:**
- Pilot team training and enablement
- Adoption metrics and tracking
- Resistance management strategies
- Champion network building
- Stakeholder engagement plans

**Core Skills:** #change-management, #document-structure, #technical-writing, #data-visualization, #ai-terminology

---

### Phase 3 Agents: Transition & Scale (Days 61-90)

#### 11. Vendor-Transition-Manager Agent (@Vendor-Transition-Manager)
**Vendor transition specialist** for contract wind-down and knowledge transfer.

**Use Cases:**
- 30/60/90-day vendor transition plans
- Knowledge transfer frameworks
- Parallel run and cutover procedures
- Stakeholder communication during transition
- Risk mitigation during vendor replacement

**Core Skills:** #vendor-transition, #change-management, #risk-assessment, #financial-modeling, #document-structure, #technical-writing

---

### Support Agents: All Phases

#### 12. Case Study Documenter Agent (@Case-Study-Documenter)
**Success story specialist** for real-world examples and metrics.

**Use Cases:**
- Vendor replacement success stories
- Before/after comparisons
- Lessons learned documentation
- Reference materials and best practices

**Core Skills:** #document-structure, #technical-writing, #data-visualization, #ai-terminology

---

#### 13. API-Integration-Specialist Agent (@API-Integration-Specialist)
**Technical integration expert** for AI APIs and enterprise connectivity.

**Use Cases:**
- AI API integration guides and tutorials
- SDK implementation and abstraction layers
- Authentication and security patterns
- Multi-provider strategies and failover
- Performance optimization for API calls

**Core Skills:** #api-integration, #code-examples, #technical-writing, #document-structure

---

### Local AI Infrastructure Agents: Data Sovereignty & Self-Hosted Deployment

#### 14. Local-AI-Infrastructure-Architect Agent (@Local-AI-Infrastructure-Architect)
**Infrastructure specialist** for designing and deploying self-hosted LLM platforms.

**Use Cases:**
- Hardware sizing for local AI deployments (GPU, CPU, RAM, storage)
- Platform selection (prefer vLLM or SGLang for serving; use llama.cpp for endpoints)
- Containerized deployment (Docker, Kubernetes)
- Air-gapped and network-isolated deployments
- High availability and load balancing configuration
- Performance optimization and quantization strategies

**Core Skills:** #local-ai-deployment, #hardware-sizing, #production-readiness, #risk-assessment

---

#### 15. Open-Source-Model-Evaluator Agent (@Open-Source-Model-Evaluator)
**Model selection specialist** for evaluating and recommending open-source LLMs.

**Use Cases:**
- Open-source model comparison and benchmarking
- License compliance assessment for commercial use
- Model selection for specific use cases (code, chat, reasoning)
- Fine-tuning feasibility and ROI analysis
- Community health and sustainability assessment
- Model upgrade and deprecation planning

**Core Skills:** #open-source-licensing, #tool-evaluation, #risk-assessment, #technical-writing

---

#### 16. Data-Sovereignty-Advisor Agent (@Data-Sovereignty-Advisor)
**Compliance specialist** for ensuring complete data control and regulatory compliance.

**Use Cases:**
- GDPR, HIPAA, CCPA compliance for AI systems
- Data classification and handling policies
- PII detection and protection strategies
- Audit trail and access control design
- Data residency and localization requirements
- Privacy-preserving AI architectures

**Core Skills:** #data-sovereignty, #risk-assessment, #legal-compliance, #document-structure

---

#### 17. Vendor-Relationship-Manager Agent (@Vendor-Relationship-Manager)
**Relationship specialist** for managing vendor negotiations and transitions.

**Use Cases:**
- AI vendor contract negotiation
- Pricing model analysis and optimization
- SLA design and enforcement
- Vendor exit strategies and professional transitions
- Multi-vendor portfolio management
- Vendor performance monitoring and accountability

**Core Skills:** #vendor-negotiation, #vendor-transition, #risk-assessment, #financial-modeling

---

#### 18. MLOps-Engineer Agent (@MLOps-Engineer)
**Operations specialist** for running production local AI infrastructure.

**Use Cases:**
- Production deployment and operations
- Monitoring, alerting, and observability setup
- Incident management and response procedures
- Capacity planning and scaling strategies
- Model lifecycle management and updates
- Cost optimization and efficiency tracking

**Core Skills:** #mlops-operations, #local-ai-deployment, #production-readiness, #metrics-analytics

---

---

## Available Skills

### Core Program Execution Skills

#### 1. Program Planning Skill (#program-planning)
**Expertise:** Creating and executing 30-60-90 day vendor replacement programs

**Provides:**
- 30-60-90 day planning frameworks
- Milestone and dependency management
- Resource allocation and budgeting
- Phase gate criteria and governance
- Program charter development

---

#### 2. Milestone Tracking Skill (#milestone-tracking)
**Expertise:** Tracking program milestones, deliverables, and dependencies

**Provides:**
- Milestone tracking templates and schedules
- Deliverable management frameworks
- Dependency mapping techniques
- Status reporting formats
- Dashboard and visualization guidance

---

#### 3. Stakeholder Management Skill (#stakeholder-management)
**Expertise:** Managing stakeholder engagement and communication

**Provides:**
- Stakeholder mapping and analysis
- Power-interest matrix frameworks
- Communication planning templates
- Engagement strategies by stakeholder type
- Resistance management techniques

---

### Documentation & Communication Skills

#### 4. Document Structure Skill (#document-structure)
**Expertise:** Information architecture and organization patterns

**Provides:**
- Logical document hierarchies
- Content organization frameworks
- Navigation and discoverability
- Template structures
- Readability optimization

---

#### 5. Technical Writing Skill (#technical-writing)
**Expertise:** Clear, concise technical communication

**Provides:**
- Writing clarity guidelines
- Active voice and readability
- Audience-appropriate language
- Effective code documentation
- Style consistency

---

#### 6. AI Terminology Skill (#ai-terminology)
**Expertise:** Consistent AI/ML terminology and definitions

**Provides:**
- Standard AI/ML terms
- Vendor-neutral language
- Concept explanations
- Terminology glossaries
- Industry standard definitions

---

#### 7. Code Examples Skill (#code-examples)
**Expertise:** Code samples, patterns, and security guidelines

**Provides:**
- Working code samples
- Integration patterns
- Security best practices
- Error handling examples
- Testing and validation

---

### Financial & Analysis Skills

#### 8. Data Visualization Skill (#data-visualization)
**Expertise:** Charts, tables, and metrics presentation

**Provides:**
- Chart selection guidance
- Dashboard design principles
- Metrics visualization patterns
- Table formatting standards
- Executive summary graphics

---

#### 9. Financial Modeling Skill (#financial-modeling)
**Expertise:** ROI calculations, TCO analysis, and cost models

**Provides:**
- ROI calculation frameworks
- Total cost of ownership (TCO) models
- Cost-benefit analysis templates
- Payback period calculations
- Budget planning and forecasting

---

### Enterprise Transition Skills

#### 10. Vendor Transition Skill (#vendor-transition)
**Expertise:** Exit planning, knowledge transfer, cutover strategies

**Provides:**
- Transition planning frameworks
- Knowledge transfer templates
- Parallel run procedures
- Cutover checklists
- Rollback strategies

---

#### 11. Risk Assessment Skill (#risk-assessment)
**Expertise:** Security, compliance, and business risk analysis

**Provides:**
- Risk identification methods
- Security assessment frameworks
- Compliance requirement mapping
- Risk scoring matrices
- Mitigation planning

---

#### 12. Change Management Skill (#change-management)
**Expertise:** Adoption strategies, training, stakeholder engagement

**Provides:**
- Change readiness assessment
- Training program design
- Adoption metrics tracking
- Resistance management
- Communication strategies

---

#### 13. Tool Evaluation Skill (#tool-evaluation)
**Expertise:** Scorecards, POC frameworks, selection criteria

**Provides:**
- Tool comparison matrices
- Evaluation scorecards
- Proof-of-concept planning
- Build vs. buy frameworks
- Vendor assessment criteria

---

### Technical Integration Skills

#### 14. API Integration Skill (#api-integration)
**Expertise:** API/SDK integration patterns and best practices

**Provides:**
- API integration patterns
- Authentication strategies
- Error handling and retry logic
- Rate limiting and throttling
- Multi-provider architectures

---

#### 15. Legal Compliance Skill (#legal-compliance)
**Expertise:** Contract law, IP protection, and vendor agreements

**Provides:**
- Contract review guidelines
- IP protection strategies
- Data processing agreements
- Licensing compliance
- Vendor exit terms

---

#### 16. Metrics Analytics Skill (#metrics-analytics)
**Expertise:** Productivity measurement and ROI validation

**Provides:**
- Productivity metrics frameworks
- Baseline measurement methods
- Performance tracking systems
- ROI validation approaches
- Continuous improvement processes

---

#### 17. Production Readiness Skill (#production-readiness)
**Expertise:** Enterprise deployment and operational excellence

**Provides:**
- Production readiness checklists
- Deployment strategies
- Monitoring and alerting
- Incident response procedures
- Operational runbooks

---

### Local AI & Data Sovereignty Skills

#### 18. Local AI Deployment Skill (#local-ai-deployment)
**Expertise:** Self-hosted LLM platforms and enterprise deployment

**Provides:**
- Platform comparison (vLLM, SGLang, TGI, llama.cpp)
- Docker and Kubernetes deployment configurations
- Air-gapped deployment procedures
- API gateway and authentication setup
- Performance optimization and quantization
- High availability configurations

---

#### 19. Hardware Sizing Skill (#hardware-sizing)
**Expertise:** GPU and server specification for AI workloads

**Provides:**
- GPU selection guide (RTX 4090, A6000, A100, H100)
- Server configuration templates by team size
- VRAM requirements by model size
- Capacity planning calculators
- TCO modeling for hardware investments
- Scaling strategies and growth projections

---

#### 20. Open Source Licensing Skill (#open-source-licensing)
**Expertise:** License compliance for AI models and tools

**Provides:**
- License classification (permissive OSS, copyleft, provider open-weights, RAIL-style, commercial EULA)
- Commercial use eligibility assessment
- License obligation management
- IP risk evaluation for AI models
- Compliance documentation templates
- Model-specific licensing guidance

---

#### 21. Data Sovereignty Skill (#data-sovereignty)
**Expertise:** Data residency, privacy, and regulatory compliance

**Provides:**
- Data classification frameworks (PUBLIC to PROHIBITED)
- GDPR, HIPAA, CCPA compliance checklists
- PII detection and handling strategies
- Data flow mapping and documentation
- Audit trail and access control design
- Privacy-preserving architecture patterns

---

#### 22. MLOps Operations Skill (#mlops-operations)
**Expertise:** Production AI system operations and maintenance

**Provides:**
- Monitoring and observability configuration
- Alerting rules and SLO frameworks
- Operational runbooks (startup, shutdown, updates)
- Incident response procedures
- Capacity planning and scaling triggers
- Cost tracking and optimization

---

#### 23. Vendor Negotiation Skill (#vendor-negotiation)
**Expertise:** Contract negotiation and vendor relationship management

**Provides:**
- Negotiation preparation frameworks
- Pricing model analysis (per-user, per-token, flat fee)
- Key contract terms and clauses
- SLA design and enforcement
- Multi-vendor portfolio strategies
- Vendor performance scorecards

---

## Build and Test Commands

This is a program execution framework without traditional build processes. However, key workflows include:

### Program Execution Workflow
1. **Phase 1 Planning (Days 1-30)**: Use Program-Manager, Executive-Strategy-Advisor, ROI-Calculator
2. **Phase 2 Pilot (Days 31-60)**: Use Implementation-Guide, Performance-Optimization-Agent, Change-Management-Coach
3. **Phase 3 Transition (Days 61-90)**: Use Vendor-Transition-Manager with all support agents
4. **Review**: Verify phase gates, track milestones, update stakeholders

### Quality Assurance Process
- **Phase Gate Reviews**: Evaluate Go/No-Go criteria at Days 30, 60, 90
- **Milestone Tracking**: Monitor deliverables and dependencies weekly
- **Risk Management**: Review risk register and mitigation plans
- **Stakeholder Engagement**: Track stakeholder satisfaction and adoption metrics

### Testing Instructions

#### Program Execution Validation
1. **Program Charter**: Validate alignment with business objectives
2. **Milestone Progress**: Track actual vs. planned completion rates
3. **Risk Mitigation**: Assess effectiveness of risk mitigation strategies
4. **Stakeholder Satisfaction**: Survey key stakeholders for feedback

#### Agent Coordination
1. **Multi-Agent Workflows**: Verify smooth handoffs between phase agents
2. **Skill Integration**: Ensure consistent application of program execution skills
3. **Documentation Quality**: Check generated program artifacts
4. **Decision Support**: Validate quality of recommendations and analysis

## Code Style Guidelines

### Documentation Standards
- **Language**: Clear, active voice with grade 10-12 reading level
- **Structure**: Logical hierarchy with H1-H6 headings
- **Examples**: Working code samples with security considerations
- **Visuals**: Tables for comparisons, charts for metrics
- **Terminology**: Consistent AI/ML terms per #ai-terminology skill

### File Organization
- **Agents**: `agents/[Agent-Name].agent.md` with YAML frontmatter
- **Skills**: `skills/[skill-name].skill.md` with markdown structure
- **Documentation**: `docs/[category]/[topic].md` with clear naming
- **Templates**: Reusable patterns within skill documentation

### Writing Style Guidelines
**DO:**
- Use simple, direct language ("Click the Deploy button")
- Write in active voice ("The system processes data")
- Include specific metrics ("Reduces costs by 40%")
- Provide clear action steps ("Follow these steps to configure...")

**DON'T:**
- Use unnecessary jargon ("Utilize the deployment functionality")
- Write in passive voice ("Data is processed by the system")
- Use vague statements ("Cost optimization is achieved")
- Create complex nested sentences

## Security Considerations

### Content Security
- **Code Examples**: Include security best practices and warnings
- **Data Handling**: Document proper data classification and handling
- **Access Control**: Reference principle of least privilege
- **Secrets Management**: Never include real credentials in examples

### Enterprise Security
- **Compliance**: Address SOC2, GDPR, HIPAA requirements in relevant docs
- **Risk Assessment**: Include security risk analysis in vendor transitions
- **Audit Readiness**: Document logging and monitoring requirements
- **IP Protection**: Address intellectual property considerations

### Tool Security
- **Principle of Least Privilege**: Agents only have necessary tools
- **Audit Logging**: All operations are logged for monitoring
- **Access Control**: Configurable based on security requirements
- **Compliance Ready**: Supports enterprise compliance needs

## Deployment Process

### Documentation Publishing
1. **Review**: Technical and editorial review of all content
2. **Validation**: Test all examples and validate claims
3. **Approval**: Stakeholder sign-off for enterprise content
4. **Publication**: Merge to main branch and update indices

### Production Readiness Package
Before scaling AI vendor replacement:
1. Complete all production readiness checklists
2. Obtain security and compliance sign-off
3. Finalize vendor transition plans
4. Deploy training and adoption programs

### Enterprise Deployment
1. **Tool Configuration**: Set appropriate security levels
2. **Access Control**: Configure role-based permissions
3. **Monitoring**: Implement usage tracking and audit logs
4. **Training**: Deploy user training and adoption programs

## Development Conventions

### Agent Development
- **YAML Frontmatter**: Include description and tools array
- **Clear Purpose**: Define agent scope and responsibilities
- **Use Cases**: List specific scenarios for agent usage
- **Skills Mapping**: Explicitly list applicable skills

### Skill Development
- **Overview**: Brief description of expertise area
- **Principles**: Core guidelines and best practices
- **Examples**: Concrete examples with DO/DON'T comparisons
- **Templates**: Reusable patterns and structures

### Documentation Patterns
- **Executive Summary**: Business value and key findings upfront
- **Step-by-Step**: Numbered lists for procedural content
- **Decision Trees**: Visual guides for complex choices
- **Case Studies**: Real-world examples with quantified results

## Common Workflows

### Multi-Agent Documentation Creation
```
1. @ROI-Calculator Create financial justification
2. @Implementation-Guide Create setup tutorial
3. @Case-Study-Documenter Document pilot results
4. @Documaster Compile comprehensive guide
```

### Enterprise Readiness Package
```
1. @Tool-Evaluation-Specialist Create evaluation scorecard
2. @Security-Risk-Compliance-Advisor Produce security checklist
3. @Vendor-Transition-Manager Create transition plan
4. @Change-Management-Coach Build training program
5. @Documaster Package for executive review
```

### Production Readiness Workflow
```
1. @Security-Risk-Compliance-Advisor Complete risk assessment
2. @Tool-Evaluation-Specialist Validate tool selection
3. @Vendor-Transition-Manager Plan transition strategy
4. @Change-Management-Coach Design adoption program
5. @Performance-Optimization-Agent Set up monitoring
6. @Executive-Strategy-Advisor Create executive summary
```

### Local AI Deployment Workflow (Data Sovereignty)
```
1. @Local-AI-Infrastructure-Architect Size hardware and select platform
2. @Open-Source-Model-Evaluator Select and validate models
3. @Data-Sovereignty-Advisor Ensure compliance (GDPR, HIPAA)
4. @MLOps-Engineer Deploy and configure production infrastructure
5. @Vendor-Relationship-Manager Negotiate any remaining vendor contracts
6. @Implementation-Guide Create user training and documentation
```

### Vendor Replacement with Local AI
```
1. @ROI-Calculator Compare cloud vs. local AI TCO
2. @Tool-Evaluation-Specialist Evaluate local platforms (vLLM, SGLang, TGI, llama.cpp)
3. @Open-Source-Model-Evaluator Select appropriate models with license compliance
4. @Local-AI-Infrastructure-Architect Design infrastructure architecture
5. @Data-Sovereignty-Advisor Validate data handling and compliance
6. @MLOps-Engineer Deploy and operate local AI platform
7. @Vendor-Transition-Manager Execute cloud-to-local transition
```

## Success Metrics

### Documentation Quality
- **Clarity**: User comprehension surveys (target: 90%+ satisfaction)
- **Accuracy**: Technical review pass rate (target: 100%)
- **Completeness**: Coverage of required topics (target: 100%)
- **Usage**: Documentation reference frequency (track engagement)

### Business Impact
- **Cost Reduction**: 60-80% vendor cost savings
- **Productivity Gain**: 1.5-2.5x FTE productivity increase
- **Adoption Rate**: 80%+ team adoption within 6 months
- **ROI Achievement**: 200%+ ROI in first year
- **Payback Period**: Less than 6 months

### Enterprise Readiness
- **Security Compliance**: 100% checklist completion
- **Risk Mitigation**: All identified risks addressed
- **Training Coverage**: 100% of affected personnel trained
- **Vendor Transition**: Zero-downtime cutover success

### Local AI Deployment
- **Data Sovereignty**: 100% local processing, zero external data transfer
- **Availability**: 99.5%+ uptime for self-hosted infrastructure
- **Cost vs. Cloud**: 60-80% lower TCO over 3 years
- **License Compliance**: 100% of models properly licensed
- **MTTR**: <30 minutes for critical issues

## Troubleshooting

### Common Issues
- **Agent Scope Creep**: Agents staying focused on their expertise
- **Inconsistent Terminology**: Using #ai-terminology skill for consistency
- **Missing Examples**: Reference #code-examples for patterns
- **Complexity**: Break complex topics into multiple focused documents
- **Tool Access**: Review each agent's `tools:` frontmatter for configured tool access

### Getting Help
- **Agent Capabilities**: Review `.agent.md` files for scope
- **Skill Guidance**: Check `.skill.md` files for best practices
- **Examples**: Reference existing documentation patterns
- **Repo Orientation**: Start with README.md for the overview and AGENTS.md for the full agent/skill map

### Performance Optimization
- **Agent Coordination**: Use appropriate agents for specific tasks
- **Skill References**: Explicitly reference skills for expertise
- **Iterative Approach**: Build documentation in stages
- **Quality Checks**: Validate content at each stage

---

**System Version:** 4.1.0 (Production-Ready Agent Framework)
**Last Updated:** December 31, 2025
**Maintained by:** FTE+AI Project Team

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

For questions or suggestions, review the specific agent or skill files for detailed guidance.