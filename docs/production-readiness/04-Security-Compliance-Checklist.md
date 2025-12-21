# Security & Compliance Checklist (Local AI)

**Scope:** Local/on-prem AI for code and QA workflows.

## Security Controls

- [ ] Data classification policy for AI prompts/outputs
- [ ] DLP rules for source code and secrets
- [ ] Secrets scanning in prompts and outputs
- [ ] RBAC + MFA enforced for all AI tools
- [ ] Network egress blocked by default
- [ ] TLS for all internal AI endpoints
- [ ] Encryption at rest for model storage and logs
- [ ] Audit logging enabled for prompts, outputs, and access
- [ ] Access reviews scheduled quarterly

## Privacy and Data Residency

- [ ] Data remains on-prem/local only
- [ ] No third-party telemetry or call-home traffic
- [ ] Data retention and deletion policies defined
- [ ] PII handling rules enforced and tested
- [ ] Synthetic data strategy for test cases

## Compliance (Select Applicable)

- [ ] SOC2 controls mapped and evidence captured
- [ ] GDPR DPIA completed (if EU data)
- [ ] HIPAA safeguards in place (if PHI)
- [ ] IP ownership reviewed and documented
- [ ] OSS license compliance for models and dependencies

## Audit Evidence

- [ ] Architecture and data flow diagrams
- [ ] Security configuration snapshots
- [ ] Risk assessment register
- [ ] Access logs and reviews
- [ ] Incident response runbook

## Signoff

- Security Lead: [Name, Date]
- Compliance Lead: [Name, Date]
- Legal Counsel: [Name, Date]
