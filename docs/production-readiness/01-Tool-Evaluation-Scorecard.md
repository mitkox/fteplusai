# Tool Evaluation Scorecard (Local AI / Data-Private)

**Goal:** Select local AI tooling that keeps data private while meeting enterprise needs.
**Scope:** Local/on-prem LLM serving, code assistance, and QA automation support.

## Shortlist (Replace with Your Top Local Vendors)

| Candidate | Deployment Model | Data Residency | Primary Use | Notes |
|-----------|------------------|----------------|-------------|-------|
| Vendor A | On-prem | Local only | Code + QA | [Replace]
| Vendor B | On-prem | Local only | LLM serving | [Replace]
| Vendor C | Local workstation or private cluster | Local only | Dev assist | [Replace]

**Examples of local-capable platforms (use only if they match your stack):**
- On-prem LLM serving: vLLM, TGI, LocalAI
- Local developer runtimes: Ollama, LM Studio
- Enterprise on-prem platforms: vendor-provided private AI stacks (replace with your list)

## Privacy Gate (Must-Pass)

All candidates must pass these to proceed:
- [ ] No data leaves local environment (no external API calls)
- [ ] Data retention controls configurable (disable provider retention)
- [ ] Network egress locked down and audited
- [ ] Audit logs available for prompts and outputs
- [ ] Access control supports RBAC and MFA
- [ ] Encryption at rest and in transit

## Scoring Framework

**Rating scale (1-10):** 9-10 exceptional, 7-8 good, 5-6 acceptable, <5 poor

| Category | Weight | Vendor A | Vendor B | Vendor C |
|----------|--------|----------|----------|----------|
| Functionality (code, QA, docs) | 25% | | | |
| Privacy & Security (local-only) | 20% | | | |
| Integration (IDE/CI/CD) | 15% | | | |
| Performance (latency/throughput) | 10% | | | |
| Reliability (SLA/uptime) | 10% | | | |
| Cost (TCO) | 10% | | | |
| Support & Vendor Maturity | 10% | | | |
| **Total (Weighted)** | **100%** | | | |

## Evidence Checklist

For each vendor, collect:
- [ ] Architecture diagram and deployment model
- [ ] Data flow diagram proving local-only data handling
- [ ] Security posture (SOC2/ISO evidence if applicable)
- [ ] Performance benchmarks on representative tasks
- [ ] Integration proof (IDE plugins, CI/CD hooks)
- [ ] TCO estimate (hardware, support, ops)
- [ ] Migration/exit plan

## Recommended POC Tasks

**Code tasks:**
- Generate unit tests for 3 representative services
- Suggest refactors on a real PR
- Identify security issues in a sample repo

**QA tasks:**
- Create regression test plan from requirements
- Generate test cases from a user story
- Detect flaky tests and propose fixes

**Acceptance criteria:**
- Pass rate >= [X%]
- Latency <= [Y seconds]
- Cost per task <= [$Z]
- Developer satisfaction >= [score]

## Decision Summary

- **Recommended:** [Vendor]
- **Rationale:** [Top 3 reasons]
- **Risks:** [Top 3 risks]
- **Mitigations:** [Top 3 mitigations]
