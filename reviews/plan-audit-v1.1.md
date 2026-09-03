# Plan Audit v1.1 — 2026-09-04

## Scope
Independent re-audit of the canonical EduSite plan after the initial control-plane bootstrap. The active implementation task remains TASK-002; this audit changes governance/roadmap only.

## Overall result
**PASS WITH IMPROVEMENTS.** The core architecture and governance model are sound. No reason was found to abandon the current frontend/Frappe strategy.

## Critical issue found
### Production hardening was sequenced after commercialization
Previous roadmap order placed multi-school commercialization before production hardening. This conflicted with the accepted stage-based security policy.

**Correction:** real-school pilot readiness and production hardening now precede multi-school commercialization.

## Important gaps found and corrections
1. **External-agent artifact persistence** — Arena/Fable or other external outputs must be captured immediately in a durable branch/repository/artifact before review when the platform permits export. Review may happen after intake; `main` still receives only verified work.
2. **Verification evidence model** — independent review must distinguish code/diff inspection, automated checks, visual/browser evidence, and claims that could not be verified.
3. **CI / stable-main expectation** — product code repositories should add automated typecheck/lint/build/tests appropriate to their stage and protect stable branches when operationally practical.
4. **Release and rollback discipline** — before production, releases must be identifiable, reversible, and tied to verified commits; migrations require rollback/restore planning.
5. **Frontend non-functional requirements** — explicit baseline added for SEO, browser/mobile support, accessibility target, performance measurement, and media handling.
6. **Frontend tenancy/deployment model not yet decided** — one-build-per-school vs runtime multi-tenant frontend configuration is intentionally deferred until evidence exists; it must be resolved by ADR before commercialization.
7. **CMS/media ownership not yet defined** — M2 must decide which website content is managed in Frappe and how uploaded media/object storage/CDN are handled.
8. **Temporary AI credits are resources, not architecture dependencies** — the product must remain maintainable if Fable, Hyperagent, Antigravity, Zed credits or a specific model disappear.
9. **State semantics** — `next_task` must not duplicate the currently active task; while TASK-002 is active, the next task remains unset until TASK-002 outcome is known.
10. **Commercial readiness beyond code** — licensing/dependency review, data export/ownership expectations, support/operations and backup/restore readiness must be addressed before broad rollout.

## Confirmed decisions
- GitHub remains canonical source of truth.
- Old repositories remain off-limits without repository-specific authorization.
- Codex remains default implementer; other agents are selected by task fit.
- Frontend remains reusable/config-driven and backend-independent.
- Frappe/ERPNext/Frappe Education + separate Bangladesh custom app remains the preferred backend direction.
- Prototype security stays proportionate; strict security applies before real production data.
- Frappe Cloud remains optional.

## Deferred decisions (intentional, not gaps)
- exact production VPS/provider and sizing;
- exact frontend hosting topology;
- final school pricing;
- exact payment/SMS providers;
- final Bangladesh result rules until requirements are validated;
- final multi-tenant frontend deployment model.

## Current project state after audit
TASK-002 remains active: review Arena Fable Stage 1 after its output is available. No Stage 2 implementation starts before that review and canonical synchronization.
