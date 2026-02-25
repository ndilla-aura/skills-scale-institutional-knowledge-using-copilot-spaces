# OctoAcme Personas

This document defines typical roles and responsibilities used in OctoAcme project docs and exercises.

For cross-functional checklists and handoff templates, see:
- [Definition of Ready / Done](./octoacme-definition-of-ready-done.md)
- [Security & QA Gating Checklist](./octoacme-security-qa-gating-checklist.md)

---

## Developers

### Role Summary
Developers design, build, test, and deliver software components. They collaborate with product and project leads to implement features that meet acceptance criteria and quality standards.

### Responsibilities
- Implement features and fixes to meet acceptance criteria
- Write and maintain tests and documentation
- Participate in design and code reviews
- Assist in estimating and planning work
- Help identify technical risks and propose mitigations

### Goals
- Deliver reliable, maintainable code
- Reduce cycle time from idea to production
- Maintain high test coverage and observability

### Typical Communication
- Daily standups and sprint planning
- PR descriptions and code review comments
- Technical design docs when needed

### Interactions
- **Product Manager**: receive and clarify acceptance criteria and feature specs
- **Project Manager**: provide estimates, surface blockers, update task status on project board
- **UX Designer**: consume design specs and wireframes; request design reviews before merge
- **QA / Tester**: hand off completed features for QA validation; address defect reports
- **Security Champion**: implement security requirements surfaced during threat modelling; act on findings from security scans
- **Data Analyst**: instrument features with agreed events/metrics; share data access for analysis

---

## Product Managers

### Role Summary
Product Managers define what should be built to deliver customer and business value. They own the product vision, prioritize the backlog, and measure outcomes.

### Responsibilities
- Define problem statements and success metrics
- Prioritize the roadmap and backlog
- Collaborate with stakeholders and engineering on trade-offs
- Validate solutions through user research and metrics

### Goals
- Maximize customer value and impact
- Make clear, data-driven prioritization decisions
- Ensure product-market fit and usability

### Typical Communication
- Weekly alignment with PM and engineering leads
- Roadmap updates and stakeholder briefings
- Acceptance criteria and feature specs

### Interactions
- **Project Manager**: align on timeline, scope changes, and risk trade-offs
- **UX Designer**: co-define user journeys and validate designs against outcomes
- **Data Analyst**: review metrics and dashboards to inform backlog priorities
- **QA / Tester**: confirm acceptance criteria are testable; sign off on QA exit criteria
- **Security Champion**: incorporate security requirements into feature specs

---

## Project Managers

### Role Summary
Project Managers coordinate delivery activities, manage schedules, risks, and communications. They enable the team to deliver on commitments efficiently.

### Responsibilities
- Create and maintain project plans and timelines
- Manage risks, dependencies, and resource constraints
- Facilitate meetings (kickoff, planning, retrospectives)
- Ensure consistent project documentation and status reporting
- Coordinate cross-team and stakeholder communication

### Goals
- Deliver projects on time and within scope
- Minimize unplanned work and escalations
- Maintain transparency and alignment across stakeholders

### Typical Communication
- Weekly status updates and stakeholder reports
- Risk registers and decision logs
- Coordination via project boards and meeting facilitation

### Interactions
- **Product Manager**: co-own roadmap alignment and scope decisions
- **Developers**: track progress, remove blockers, maintain project board
- **UX Designer**: schedule design checkpoints within the sprint/milestone timeline
- **QA / Tester**: ensure QA phases are accounted for in the project timeline
- **Security Champion**: include security review gates in project milestones
- **Data Analyst**: coordinate data requirements and reporting timelines

---

## UX Designer

### Role Summary
UX Designers craft user-centred experiences by translating user research and product requirements into intuitive designs. They partner closely with Product Managers and Developers to ensure features are usable, accessible, and aligned with OctoAcme brand standards.

### Responsibilities
- Conduct or synthesise user research to inform design decisions
- Create wireframes, prototypes, and high-fidelity design specs
- Define and maintain interaction patterns and design-system components
- Facilitate design reviews with engineering and product
- Validate designs through usability testing and feedback loops

### Goals
- Reduce user friction and support adoption of new features
- Maintain design consistency across the product
- Ensure features meet accessibility standards (e.g., WCAG 2.1 AA)

### Typical Communication
- Design critiques and review sessions during sprint planning/execution
- Design specs shared via design tools (e.g., Figma) linked in PRs/issues
- Async feedback via issue comments and PR reviews

### Interactions
- **Product Manager**: co-define user journeys; align on scope and user research priorities
- **Developers**: hand off design specs and assets; review implemented UI before QA
- **Project Manager**: communicate design dependency timelines and review schedule
- **QA / Tester**: share interaction specifications so test cases cover UX acceptance criteria
- **Data Analyst**: share behavioural metrics to validate design hypotheses

---

## QA / Tester

### Role Summary
QA Engineers / Testers protect product quality by validating that features meet acceptance criteria, are free of critical defects, and perform reliably. They own the QA column on the project board and are the last gate before release.

### Responsibilities
- Author and maintain test plans, test cases, and automation scripts
- Execute functional, regression, and exploratory testing
- Log, triage, and track defects to resolution
- Define and uphold the Definition of Done for QA sign-off
- Collaborate with Developers on testability requirements and CI test suites
- Participate in pre-release smoke tests and post-deploy verification

### Goals
- Prevent defect leakage to production
- Improve test automation coverage sprint-over-sprint
- Provide fast, actionable feedback to developers

### Typical Communication
- QA status updates in daily standups
- Defect reports and test summary notes attached to issues/PRs
- QA sign-off comment before items move to Done column

### Interactions
- **Developers**: receive features for validation; return defect reports; pair on test automation
- **Product Manager**: clarify acceptance criteria; confirm QA exit criteria before sprint review
- **Project Manager**: report QA progress and surface risks to release timelines
- **UX Designer**: receive interaction specs to build UI/UX test cases
- **Security Champion**: collaborate on security test cases aligned with threat models

---

## Data Analyst

### Role Summary
Data Analysts turn product instrumentation and operational data into actionable insight. They partner with Product Managers and Developers to define metrics, build dashboards, and surface trends that guide prioritisation and assess feature impact.

### Responsibilities
- Define and document key product and operational metrics
- Build and maintain dashboards for team-facing and stakeholder-facing reporting
- Analyse experiment (A/B test) results and provide recommendations
- Identify data quality issues and work with engineering to resolve them
- Support retrospectives with data-driven inputs

### Goals
- Provide reliable, timely metrics that inform decisions
- Reduce reliance on gut-feel prioritisation
- Ensure data instrumentation is in place before features ship

### Typical Communication
- Metrics reviews in sprint/milestone retrospectives
- Dashboard links shared in weekly status updates
- Async analysis reports linked from project issues or wiki

### Interactions
- **Product Manager**: co-define success metrics and OKRs; provide analysis to drive backlog decisions
- **Developers**: align on instrumentation spec (events, properties) before feature build; validate data pipelines
- **Project Manager**: supply data for stakeholder status reports and retrospective summaries
- **QA / Tester**: validate that instrumentation events fire correctly in test environments
- **UX Designer**: share engagement and funnel data to validate design hypotheses

---

## Security Champion

### Role Summary
Security Champions are team members (often a Developer or dedicated Security Engineer) responsible for embedding security practices into the delivery lifecycle. They act as the bridge between the central security team and delivery squads.

### Responsibilities
- Conduct lightweight threat modelling for new features and integrations
- Review pull requests for common security vulnerabilities (OWASP Top 10)
- Maintain and act on findings from automated security scans (SAST, SCA, secrets scanning)
- Own the security section of the [Security & QA Gating Checklist](./octoacme-security-qa-gating-checklist.md)
- Escalate high-severity findings to the Project Manager and Product Manager
- Lead or support security incident response triage

### Goals
- Shift security left — catch issues during design and development, not in production
- Maintain a low mean-time-to-remediate (MTTR) for security findings
- Ensure security requirements are first-class citizens in acceptance criteria

### Typical Communication
- Security review notes attached to relevant PRs and issues
- Threat model summaries in project documentation
- Escalation via the risk register for high-impact findings

### Interactions
- **Developers**: pair on secure coding practices; review PRs; guide remediation of scan findings
- **Product Manager**: raise security requirements for inclusion in acceptance criteria; assess risk trade-offs
- **Project Manager**: add security review milestones to project plan; update risk register with security risks
- **QA / Tester**: co-design security test cases; validate fixes for security defects
- **Data Analyst**: ensure data handling and storage meets privacy and compliance requirements

---

## Interaction Map

The table below summarises ownership across key delivery activities. Use it as a quick-reference RACI-lite guide.

| Activity | Project Manager | Product Manager | Developer | UX Designer | QA / Tester | Data Analyst | Security Champion |
|---|---|---|---|---|---|---|---|
| Sprint / milestone planning | **A** | **R** | C | C | C | C | C |
| Backlog prioritisation | C | **A/R** | C | C | I | R | C |
| Design spec & review | I | C | C | **A/R** | C | I | I |
| Feature development | C | I | **A/R** | C | I | I | C |
| QA sign-off | I | C | C | C | **A/R** | I | C |
| Security review gate | C | C | C | I | C | I | **A/R** |
| Metrics definition | C | **A/R** | C | C | I | R | I |
| Release readiness | **A** | C | C | I | R | I | R |
| Risk & incident comms | **A/R** | C | C | I | I | I | R |
| Retrospective data & actions | **A** | R | R | R | R | R | R |

*A = Accountable, R = Responsible, C = Consulted, I = Informed*

---

## How these personas are used in the exercise
- Use these persona definitions to frame scenarios and sample interactions in the Skills Exercise.
- Each persona can be used as a persona prompt for Copilot Spaces to shape role-specific guidance.

