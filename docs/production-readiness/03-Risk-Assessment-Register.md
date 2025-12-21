# Risk Assessment Register (Local AI)

**Scope:** Local AI deployment for replacing vendor dev/test capacity.

## Risk Scoring

- **Likelihood (1-5):** 1 rare, 5 almost certain
- **Impact (1-5):** 1 negligible, 5 catastrophic
- **Score:** Likelihood x Impact

## Risk Register

| ID | Risk | Category | Likelihood | Impact | Score | Owner | Mitigation | Status |
|----|------|----------|------------|--------|-------|-------|------------|--------|
| R1 | Sensitive code exposure via prompts | Security | 3 | 4 | 12 | Security | DLP + prompt scanning + policy | Open |
| R2 | Model output quality regression | Quality | 3 | 3 | 9 | Eng | Eval harness + human review | Open |
| R3 | Local infra capacity bottleneck | Ops | 3 | 4 | 12 | Platform | Load testing + autoscale | Open |
| R4 | Vendor lock-in to local stack | Business | 2 | 3 | 6 | CTO | Portability plan + open formats | Open |
| R5 | Low adoption by dev/QA teams | Change | 3 | 3 | 9 | R&D VP | Training + champions + KPI | Open |
| R6 | Compliance audit gaps | Compliance | 2 | 4 | 8 | Compliance | Audit evidence plan | Open |

## Risk Review Cadence

- Weekly during POC
- Biweekly during rollout
- Quarterly after production

## Escalation Criteria

- Any score >= 13 requires exec review
- Any security incident triggers incident response runbook
