# Frontend Specification

## Goal
A premium, reusable, white-label public high-school website frontend for Bangladesh.

## Experience
Must feel academic, credible, mature, modern and professional. Avoid generic SaaS, childish education templates, old government-portal styling, excessive gradients/glassmorphism/rounded cards/animation.

## Visual direction
- deep academic navy
- refined royal blue
- restrained warm gold
- white and warm neutral surfaces
- strong typography hierarchy
- modest radii
- border-first surfaces
- restrained shadows
- subtle motion, reduced-motion aware

## Responsive targets
Design deliberately for approximately 360px, 390px, 430px, tablet, laptop and large desktop.

## Accessibility foundation
Semantic HTML, logical headings, visible focus, keyboard usability, contrast, labels and reduced-motion support. Target WCAG 2.2 AA where practical for the public production site; exceptions must be documented rather than silently ignored.

## SEO baseline
Public pages must be built for strong organic discoverability, not treated as a post-launch plugin task.

Required production direction:
- server-rendered/static-rendered public content where appropriate;
- unique page titles and meta descriptions;
- canonical URLs;
- robots and sitemap strategy;
- semantic heading hierarchy and crawlable navigation;
- Open Graph/social metadata;
- structured data where genuinely applicable (for example Organization/EducationalOrganization, BreadcrumbList, Article/NewsArticle/Event as appropriate and valid);
- stable human-readable URLs;
- redirect strategy when routes change;
- later bilingual support must account for canonical/hreflang rules if separate localized URLs are introduced;
- no important public information hidden behind client-only rendering without a justified reason.

SEO claims must be checked with actual rendered output and crawl/indexability tooling before production.

## Speed & Core Web Vitals baseline
Performance is a product requirement.

Design/engineering rules:
- prefer server components/rendering for public content where practical;
- minimize client-side JavaScript and hydration;
- lazy-load below-the-fold media/components where appropriate;
- optimize and correctly size images; use responsive image delivery;
- avoid layout shift by reserving media dimensions;
- keep fonts, third-party scripts and animation restrained;
- cache static/public data safely where appropriate;
- avoid heavyweight libraries when native/platform features are sufficient;
- measure performance repeatedly on representative mobile conditions.

Initial production targets for representative public pages, subject to evidence-based refinement:
- LCP <= 2.5 s at the 75th percentile;
- INP <= 200 ms at the 75th percentile;
- CLS <= 0.1 at the 75th percentile;
- Lighthouse Performance/SEO/Accessibility/Best Practices should generally target 90+ on representative pages, but Core Web Vitals and real-user behavior take priority over chasing synthetic scores.

## Frontend security baseline
Prototype security remains proportionate, but the frontend architecture must not create avoidable production debt.

Required direction:
- no production secrets or privileged API credentials in browser bundles;
- validate/sanitize untrusted rich content at the correct trust boundary;
- safe handling of external links, embeds and downloadable files;
- security headers appropriate to deployment, including CSP strategy, HSTS in production HTTPS deployments, X-Content-Type-Options, Referrer-Policy and a conservative Permissions-Policy where appropriate;
- dependency review/scanning before production;
- no unsafe HTML injection without explicit sanitization/review;
- authentication/session logic, when added later, must use production-appropriate secure cookie/token practices and receive independent review.

Do not over-engineer these controls during the visual prototype; enforce the full gate before real school data/production launch.

## Android-app readiness
The website must be designed so a future Android app can be built without reimplementing the school backend or scraping the website.

Architecture requirements:
- business/domain data comes through a documented backend/API layer, not DOM scraping;
- web UI must not become the only place where essential business rules exist;
- Frappe/API contracts should be reusable by web and future mobile clients;
- media/file URLs and authentication flows should be mobile-client compatible;
- domain models should remain platform-neutral where practical;
- deep-linkable stable public URLs should be preserved;
- notification architecture should later allow push notifications without coupling them to browser-only code;
- if offline/installable behavior is useful, PWA capabilities may be added as an intermediate convenience, but PWA is not a substitute for the future native Android app unless product requirements say so.

Preferred future path after the web/backend stabilizes:
1. reuse the same Frappe/API backend;
2. evaluate a thin PWA for immediate installability if commercially useful;
3. build a dedicated Android-capable app client (likely Expo/React Native or another justified framework) using the same APIs, auth model and domain contracts;
4. decide the exact mobile framework by ADR based on requirements at that time rather than freezing it prematurely.

## Non-functional baseline
Before M1 handoff, verify or explicitly document:
- no unintended horizontal overflow at target widths;
- reasonable support for current mainstream Chrome/Edge/Firefox/Safari and modern Android/iOS browsers;
- semantic page metadata, titles/descriptions, canonical/robots/sitemap strategy appropriate to deployment;
- image sizing/optimization and stable aspect ratios to control layout shift;
- performance measured with repeatable tooling rather than visual impression alone;
- print behavior for result/routine interfaces where those features require printing;
- graceful loading, empty, error and missing-content states for dynamic data surfaces;
- dependency/license review before commercial release.

## Main public routes
See `ARCHITECTURE.md`.

## Important UX rules
- homepage: about 9–10 major visual groups;
- results: internal examination result lookup;
- routine: intentional mobile presentation;
- contact: no fake successful submission before persistence exists;
- mock data: initially small and realistic;
- bilingual-ready architecture, full bilingual implementation deferred.

## Deferred architecture decision
The frontend deployment/tenancy model is not yet frozen: one build/deployment per school versus runtime multi-school configuration must be evaluated after the demo architecture exists and resolved by ADR before broad commercialization.
