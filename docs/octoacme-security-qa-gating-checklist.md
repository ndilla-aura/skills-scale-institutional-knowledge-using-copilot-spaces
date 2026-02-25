# OctoAcme — Security & QA Gating Checklist

This checklist defines the security and QA gates that must be satisfied before a feature progresses from development to release. It aligns with the project board's QA column and the [Release & Deployment](./octoacme-release-and-deployment.md) pre-release requirements.

Owners: **Security Champion** (security items) and **QA / Tester** (QA items). See [Roles & Personas](./octoacme-roles-and-personas.md) for full role descriptions.

---

## Gate 1 — Development Complete (before moving to QA column)

### Automated Quality Checks (CI)
- [ ] All unit and integration tests pass in CI
- [ ] Linting / static analysis passing with no new violations
- [ ] SAST scan completed; no unresolved **High** or **Critical** severity findings
- [ ] SCA (dependency) scan completed; no unresolved **High** or **Critical** CVEs
- [ ] Secrets scanning passing — no credentials or API keys committed

### Code Review
- [ ] PR approved by at least one Developer peer
- [ ] Security Champion reviewed PR for security-sensitive changes (auth, data handling, third-party integrations, infrastructure config)

### Developer Self-Certification
- [ ] Feature runs end-to-end in the development environment
- [ ] No known regressions introduced (smoke-tested locally)
- [ ] PR description includes issue link, acceptance criteria reference, and test notes

---

## Gate 2 — QA Sign-off (before moving to Done column)

### Functional Testing
- [ ] Test plan authored and reviewed against acceptance criteria
- [ ] All acceptance criteria test cases executed (pass/fail/blocked recorded)
- [ ] Edge cases and negative test scenarios covered
- [ ] Regression suite run; no new failures introduced

### UX / Accessibility
- [ ] UI implementation reviewed against UX design spec
- [ ] Basic accessibility check completed (keyboard navigation, colour contrast, screen reader spot-check)

### Security Testing
- [ ] Security test cases derived from threat model or OWASP Top 10 executed
- [ ] Penetration / fuzzing tests run for high-risk surfaces (if applicable)
- [ ] Data privacy requirements validated (PII handling, data retention)

### Performance
- [ ] Load / performance tests run for user-facing or high-traffic changes (if applicable)
- [ ] No significant latency regressions detected in staging

### QA Sign-off
- [ ] Test summary documented: total cases, passed, failed, blocked
- [ ] All **Critical** and **High** defects resolved or formally accepted with a mitigation plan
- [ ] QA / Tester sign-off comment added to issue or PR

---

## Gate 3 — Release Readiness (pre-release, aligns with [Release & Deployment](./octoacme-release-and-deployment.md))

### Security & Compliance
- [ ] Final security scan on release candidate passing
- [ ] Secrets rotation completed if credentials were rotated as part of the release
- [ ] Privacy impact assessment completed (if new personal data is processed)
- [ ] Compliance sign-off obtained (if required by data residency or regulatory controls)

### QA & Stability
- [ ] Smoke tests prepared and ready to run post-deploy
- [ ] Rollback tested in staging (or rollback plan is documented and validated)
- [ ] Monitoring / alerting in place for new failure modes

### Documentation
- [ ] Release notes drafted and reviewed by Product Manager
- [ ] Runbook updated for any new operational procedures
- [ ] Data Analyst confirmed instrumentation is live in the release candidate

### Go / No-Go
- [ ] Project Manager has reviewed checklist and confirmed go/no-go decision
- [ ] Security Champion has signed off on security gate
- [ ] QA / Tester has signed off on QA gate
- [ ] Product Manager has confirmed acceptance

---

## Defect Severity Reference

| Severity | Definition | SLA (fix before release?) |
|---|---|---|
| Critical | Data loss, security breach, production outage | Yes — must fix |
| High | Major feature broken, significant user impact, exploitable security issue | Yes — must fix or accepted risk sign-off |
| Medium | Feature partially broken, workaround exists | Recommended — schedule in next sprint |
| Low | Minor cosmetic or non-blocking issue | Optional — backlog |

---

*See also: [Roles & Personas](./octoacme-roles-and-personas.md) | [Definition of Ready & Done](./octoacme-definition-of-ready-done.md) | [Execution & Tracking](./octoacme-execution-and-tracking.md) | [Release & Deployment](./octoacme-release-and-deployment.md)*
