# ADR-008 — SEO, Performance and Future Mobile-Client Readiness
Status: Accepted

## Context
EduSite must provide a very strong public website experience and later allow an Android app to be created without rebuilding or scraping the school backend.

## Decision
1. SEO and performance are first-class architecture requirements from the frontend stage, not post-launch add-ons.
2. Public indexable content should use server/static rendering where appropriate, with metadata/canonical/sitemap/robots/structured-data support designed in.
3. Core Web Vitals and repeatable performance measurements are release evidence.
4. Shared school data/business rules live behind documented backend/API/domain contracts; they must not exist only inside the web UI.
5. A future Android/mobile client will consume the same backend/API/auth/media contracts as the web product.
6. PWA capability may be used as an intermediate convenience, but does not replace a dedicated app by default.
7. The exact Android framework is deferred until the backend/API is stable and will be chosen by a later ADR.

## Consequences
- frontend work must control client JavaScript, media, fonts and rendering strategy;
- backend/API work must remain client-neutral enough for web and mobile;
- SEO/performance/security checks become explicit release gates;
- future app development should require a new client UI, not a new school-management backend.
