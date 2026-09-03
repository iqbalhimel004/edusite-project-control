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

Exact numeric performance budgets may be frozen after the real frontend environment and representative pages exist.

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
