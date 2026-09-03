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
17. Accessibility/performance/SEO/browser audit
18. Independent visual critique + fixes
19. Final regression, dependency/license review and handoff

M1 frontend work must preserve strong SEO/server-rendering, low client-JavaScript overhead, good Core Web Vitals potential, production-safe frontend boundaries, and future Android/mobile API reuse.

Important: externally generated code/artifacts must be durably captured before temporary tool/session access can expire. Capture does not imply verification or approval.

This sequence is not sacred. Material changes require documented rationale/ADR; minor sequencing refinements may be updated directly in the roadmap.

## M2 — Frappe Backend Prototype
- install/configure Frappe/ERPNext/Frappe Education
- create demo school
- map ready-made capabilities vs Bangladesh gaps
- define CMS/content ownership and uploaded-media strategy
- establish documented API/data contracts reusable by web and future mobile clients
- validate authentication/media patterns for future mobile compatibility
- validate backup/export expectations for school-owned data

## M3 — Bangladesh School Core
- class/section/group model
- internal examination/result model
- marks/GPA/report card/tabulation as required
- teacher/student/guardian workflows
- attendance and routine integration
- keep shared business rules in backend/domain logic rather than web-only components

## M4 — Portal & Operations
- student/guardian/teacher experiences as justified
- SMS integration
- fee/payment integrations when commercially justified
- operational reports
- define notification model so future push notifications can be added cleanly

## M5 — Production Pilot Readiness & Hardening
Must occur before onboarding real schools at commercial scale.
- credential rotation and secret management
- authentication/RBAC/authorization audit
- tenant/site isolation audit
- privacy controls
- rate limiting and abuse protection where needed
- SEO crawl/indexability validation on production-like deployment
- Core Web Vitals/performance measurement on representative pages/devices
- production security headers and frontend security review
- backup and restore validation
- release identification and rollback procedure
- migration rollback/restore planning
- deployment hardening
- production security review
- monitoring/alerting baseline
- support/incident ownership baseline

## M6 — Multi-school Commercialization
Only after M5 exit criteria pass for the intended production environment.
- tenant/site provisioning
- domain automation
- frontend tenancy/deployment model finalized by ADR
- package/billing operations
- operational monitoring and support
- dependency/license compliance review maintained
- data export/ownership expectations documented
- capacity planning based on measured usage

## M7 — Android / Mobile Client
Can begin after the backend/API/auth contracts are stable enough to avoid duplicating business logic.
- evaluate whether a PWA provides useful immediate installability/offline value;
- define Android app requirements and user roles;
- select mobile framework by ADR (Expo/React Native is a likely candidate, not pre-decided);
- reuse existing Frappe/API/auth/media contracts rather than rebuilding backend logic;
- add push notifications, app-specific caching/offline behavior and deep linking as justified;
- independently review mobile authentication/privacy/security before production release.
