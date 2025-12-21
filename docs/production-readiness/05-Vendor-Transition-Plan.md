# 30-60-90 Day Vendor Transition Plan

**Agent:** @Vendor-Transition-Manager (Phase 3 Lead)
**Program:** FTE+AI Vendor Replacement
**Vendor:** [Test Vendor Name]
**Scope:** External developers and testers supporting [products/teams]
**Goal:** Transition to internal AI-augmented team without delivery disruption
**Program Start:** [Date]
**Target Cutover:** Day 90

## Program Assumptions

- Vendor provides [X] developers and [Y] testers
- Phase 1 (Days 1-30) planning completed
- Phase 2 (Days 31-60) pilot validated
- Phase 3 (Days 61-90) ready for full transition
- Codebase and test suites are accessible internally
- AI tools selected and operational
- No production downtime allowed

## 30-60-90 Day Execution Plan

### Phase 1: Planning & Preparation (Days 1-30)
**Led by:** @Program-Manager
- [ ] Contract review and exit clauses documented (@Legal-Contract-Advisor)
- [ ] Business case and ROI validated (@ROI-Calculator)
- [ ] Tool evaluation completed (@Tool-Evaluation-Specialist)
- [ ] Risk assessment and security plan (@Security-Risk-Compliance-Advisor)
- [ ] Knowledge transfer scope agreed
- [ ] RACI defined and approved
- [ ] Communication plan approved (@Change-Management-Coach)
- [ ] **Phase Gate:** Day 30 Go/No-Go decision

### Phase 2: Pilot & Validation (Days 31-60)
**Led by:** @Implementation-Guide, @Performance-Optimization-Agent
- [ ] Pilot team onboarding and training
- [ ] Architecture walkthroughs completed
- [ ] Code ownership map created
- [ ] Test suite inventory and coverage map
- [ ] Runbooks and deployment docs updated
- [ ] Tribal knowledge interviews completed
- [ ] Parallel run initiated with metrics tracking
- [ ] Quality and velocity compared weekly
- [ ] Adoption metrics monitored (@Change-Management-Coach)
- [ ] **Phase Gate:** Day 60 Go/No-Go decision

### Phase 3: Transition & Scale (Days 61-90)
**Led by:** @Vendor-Transition-Manager
- [ ] Team-wide deployment and training
- [ ] Vendor contract wind-down initiated
- [ ] Final knowledge transfer completion
- [ ] Production cutover execution
- [ ] Vendor access removed after cutover
- [ ] Post-cutover monitoring increased
- [ ] Lessons learned documented (@Case-Study-Documenter)
- [ ] **Phase Gate:** Day 90 Production readiness signoff

## RACI (Key Activities)

| Activity | Responsible | Accountable | Consulted | Informed |
|----------|-------------|-------------|-----------|----------|
| Contract exit plan | Legal | CFO | Vendor Mgr | CTO |
| Knowledge transfer | Eng Lead | R&D VP | Vendor Team | QA Lead |
| AI workflow rollout | Eng Lead | CTO | Security | Teams |
| Cutover decision | R&D VP | CTO | Security/QA | Execs |

## Knowledge Transfer Checklist

- [ ] Architecture diagrams and ADRs
- [ ] Codebase tour (modules, ownership)
- [ ] Test strategy and regression scope
- [ ] CI/CD pipelines and env configs
- [ ] Known bugs and workarounds
- [ ] Release calendar and dependencies

## Parallel Run Success Criteria

- Quality parity or better (defect rate <= baseline)
- Cycle time within +/- 10% of baseline
- Test coverage maintained or improved
- AI outputs reviewed and approved by humans

## Cutover Checklist

- [ ] All KT artifacts delivered and reviewed
- [ ] Internal team on-call coverage established
- [ ] Production monitoring dashboards active
- [ ] Security sign-off for AI workflows
- [ ] Rollback plan documented

## Communication Plan

- Weekly status update to stakeholders
- Vendor coordination call twice weekly during KT
- Exec summary at end of each phase

## Risks and Mitigations

| Risk | Mitigation |
|------|------------|
| Vendor knowledge gaps | Extra KT sessions + recorded walkthroughs |
| Productivity dip | Increase overlap period + training |
| AI quality regression | Human review thresholds + eval harness |
| Stakeholder resistance | Change management + transparent comms |
