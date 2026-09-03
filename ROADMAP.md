# EduSite Roadmap

## M0 — Governance & Project Continuity
Goal: make GitHub, not chat history, the project source of truth.
- [x] Canonical plan defined
- [x] Governance model defined
- [x] Private remote control repository created
- [x] Baseline docs committed, reviewed and merged to `main`

## M1 — Sellable Frontend Demo
Current priority.

### Fable/Arena stages
0. Architecture planning — **APPROVED**
1. Foundation + design-system preview — **IN PROGRESS / NOT VERIFIED**
2. Data/config architecture
3. Global shell: utility bar, header, navigation, footer
4. Homepage Part A
5. Homepage Part B
6. Homepage Part C
7. About group
8. Teachers / staff / managing committee
9. Notices / news / events
10. Admission / downloads
11. Academics / classes / calendar
12. Routine
13. Internal results
14. Gallery
15. Contact
16. Mobile audit
17. Accessibility/performance audit
18. Independent visual critique + fixes
19. Final regression and handoff

This sequence is not sacred. Material changes require documented rationale/ADR; minor sequencing refinements may be updated directly in the roadmap.

## M2 — Frappe Backend Prototype
- install/configure Frappe/ERPNext/Frappe Education
- create demo school
- map ready-made capabilities vs Bangladesh gaps
- establish API contract/provider integration

## M3 — Bangladesh School Core
- class/section/group model
- internal examination/result model
- marks/GPA/report card/tabulation as required
- teacher/student/guardian workflows
- attendance and routine integration

## M4 — Portal & Operations
- student/guardian/teacher experiences as justified
- SMS integration
- fee/payment integrations when commercially justified
- operational reports

## M5 — Multi-school Commercialization
- tenant/site provisioning
- domain automation
- backups/restore testing
- monitoring
- package/billing operations

## M6 — Production Hardening
- credential rotation
- secret management
- RBAC/authorization audit
- tenant isolation audit
- privacy controls
- rate limiting
- backup/restore validation
- deployment hardening
- production security review
