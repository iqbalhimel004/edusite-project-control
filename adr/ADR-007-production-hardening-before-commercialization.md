# ADR-007 — Production Hardening Before Multi-school Commercialization

Status: **Accepted**

## Context
The original roadmap placed multi-school commercialization before the production-hardening milestone. That ordering conflicted with the accepted security principle that strict security/privacy controls apply before real production school data and production rollout.

## Decision
A production-pilot readiness/hardening milestone must pass before broad multi-school commercialization.

The hardening gate includes, as applicable to the intended environment: credential rotation, secret management, authentication/RBAC review, tenant isolation, privacy controls, backup/restore validation, rollback/release procedures, deployment hardening, monitoring and production security review.

## Consequences
- Prototype development remains lightweight and pragmatic.
- Commercial scale cannot be used as the point at which production security is first addressed.
- Pilot readiness can be evidence-based and proportional; this ADR does not require enterprise complexity during early development.
