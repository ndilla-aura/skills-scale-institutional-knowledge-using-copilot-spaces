# OctoAcme — Definition of Ready & Done

This document provides cross-functional checklists that help the team agree on when work is ready to start and when it is truly complete. Use these alongside the [roles and personas](./octoacme-roles-and-personas.md) and [Security & QA Gating Checklist](./octoacme-security-qa-gating-checklist.md).

---

## Definition of Ready (DoR)

A work item (user story, bug, or task) is **Ready** to be pulled into a sprint when all of the following are true:

### Product / Requirements
- [ ] Clear problem statement and user story written (e.g., "As a [persona] I want [goal] so that [benefit]")
- [ ] Acceptance criteria are specific, measurable, and testable
- [ ] Scope is understood — out-of-scope items are explicitly noted
- [ ] Dependencies on other teams or services are identified and unblocked (or a plan exists)

### Design
- [ ] UX Designer has provided wireframes or design spec (if UI is involved)
- [ ] Designs have been reviewed by the Product Manager and a Developer
- [ ] Accessibility requirements are noted in the design spec

### Engineering
- [ ] Technical approach is agreed (spike completed if needed)
- [ ] Estimated by the team (story points or t-shirt size)
- [ ] Security Champion consulted for features with data handling, auth, or new integrations

### Data & Metrics
- [ ] Success metrics defined by Data Analyst and Product Manager
- [ ] Instrumentation/event tracking requirements documented before development starts

---

## Definition of Done (DoD)

A work item is **Done** when all of the following are true:

### Development
- [ ] Code implemented and self-reviewed by the author
- [ ] Automated tests written (unit, integration) and passing in CI
- [ ] Security scan (SAST/SCA) passing with no unresolved high/critical findings
- [ ] Code reviewed and approved by at least one other Developer
- [ ] PR linked to the relevant issue; branch merged to main/trunk

### Design Verification
- [ ] UX Designer has reviewed the implementation against the design spec (if UI is involved)
- [ ] Accessibility spot-check completed

### QA Sign-off
- [ ] QA / Tester has executed the test plan against acceptance criteria
- [ ] No open critical or high-severity defects
- [ ] QA sign-off comment added to the issue or PR

### Security
- [ ] Security Champion has reviewed or signed off on security-sensitive changes
- [ ] Secrets / credentials not hardcoded; environment variable usage confirmed

### Data
- [ ] Instrumentation events fire correctly in staging (validated by Data Analyst or Developer)
- [ ] Dashboard or metric updated if the feature changes a tracked flow

### Documentation & Release
- [ ] User-facing documentation or in-app help updated (if applicable)
- [ ] Release notes entry drafted
- [ ] Project board card moved to **Done** column

---

## Role Handoff Checklist

Use this checklist when ownership of a work item transfers between roles.

### Developer → QA / Tester
- [ ] PR merged to the staging/test branch
- [ ] Test environment updated and smoke-tested by Developer
- [ ] Acceptance criteria and known edge cases documented in the issue
- [ ] Any environment-specific setup notes shared with QA

### QA / Tester → Developer (defect return)
- [ ] Defect logged with steps to reproduce, expected vs. actual, environment, and severity
- [ ] Screenshots or logs attached
- [ ] Original issue/PR linked

### Developer → Security Champion (security review)
- [ ] Threat model or security notes drafted in the issue
- [ ] SAST/SCA scan results attached or linked
- [ ] Areas of concern highlighted for Security Champion review

### QA / Tester → Project Manager (release go/no-go)
- [ ] Test summary report completed (passed, failed, blocked counts)
- [ ] All critical defects resolved or formally accepted as known issues
- [ ] QA sign-off recorded in the issue or release tracking doc

### Product Manager → Stakeholders (feature complete)
- [ ] Release notes reviewed and approved
- [ ] Go-live communication drafted (if required)
- [ ] Success metrics baseline captured by Data Analyst

---

*See also: [Roles & Personas](./octoacme-roles-and-personas.md) | [Security & QA Gating Checklist](./octoacme-security-qa-gating-checklist.md) | [Execution & Tracking](./octoacme-execution-and-tracking.md)*
