# Security & Privacy Policy by Stage

## Principle
Use proportionate security. Early development should not be slowed by disproportionate enterprise hardening, but production must not inherit prototype shortcuts unnoticed.

## Prototype/development stage
Priority:
- speed
- iteration
- experimentation

Minimum baseline:
- do not intentionally publish real secrets in public repositories;
- do not intentionally embed production credentials in client-side code;
- prefer disposable/dev-only credentials;
- use environment variables where easy and natural;
- do not use real sensitive school/student data for development unless explicitly approved.

Temporary development usernames/passwords/API tokens do not require elaborate secret-management processes at this stage if the exposure is low-risk and credentials are disposable.

## Production gate
Before real school data or production deployment:
- rotate/revoke temporary credentials;
- establish proper secret management;
- audit authentication/RBAC/authorization;
- verify tenant/site isolation;
- verify privacy controls;
- implement/verify backups and restore procedures;
- add appropriate rate limiting;
- review API permissions and session/cookie handling;
- perform deployment/security hardening;
- independently review high-risk modules.

## High-risk modules requiring independent review
- authentication/authorization
- student/guardian personal data
- tenant isolation
- exam/result calculations
- fee/payment logic
- database migrations
- production deployment/security logic
