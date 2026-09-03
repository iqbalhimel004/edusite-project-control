# Arena Fable Prompt 001 — Frontend Foundation + Design System Preview

## Project context
Build a premium, reusable, white-label public website frontend for Bangladeshi secondary/high schools. Demo school: **Sunrise Model High School**. The future backend will use Frappe Framework + ERPNext + Frappe Education + Bangladesh-specific modules, but this task is frontend-only.

## Frozen architecture
- Prefer environment-supported Next.js + React + TypeScript + Tailwind + App Router.
- Server-first where supported; client components only where interaction actually requires them.
- UI must remain separated from typed domain models/data provider; mock provider now, Frappe provider later.
- Controlled white-label customization: identity, theme tokens, section visibility/order and limited variants. No drag-and-drop page builder.
- Bilingual-ready via a minimal `LocalizedString { en: string; bn?: string }`; no language switcher yet.
- Premium academic visual direction: deep navy, refined royal blue, restrained warm gold, white/warm neutrals; modest radius/shadows; no excessive gradients/glassmorphism/animation.
- Deliberate mobile design for roughly 360/390/430px, tablet and desktop.
- Accessibility foundation: semantic HTML, logical headings, visible focus, keyboard usability, contrast, reduced motion.

## Current task only
Implement **Stage 1 — Frontend Foundation + Design System Preview**.

### Build
1. Minimal clean application foundation using Arena-supported versions.
2. Central fictional school configuration: name, short name, motto, EIIN placeholder, established year, board, address, phone, email, default locale, head-teacher title.
3. Semantic theme tokens: primary/secondary/accent/background/surface/muted/foreground/border/status plus restrained radius/shadow tokens; designed for later config-driven overrides.
4. Homepage-section config **skeleton only**: conceptually `id`, `enabled`, `order`, optional supported `variant`; no page builder.
5. Minimal localization helper/type; English default; no language switcher.
6. Base reusable components only: `Container`, `Section`, `SectionHeading`, `Button`, `Badge`, `SkipLink` (or justified equivalents).
7. Temporary `/` route as a polished **"Frontend Design System — Foundation Preview"** showing Sunrise Model High School identity, typography hierarchy, token swatches, neutral surfaces, buttons, badges, spacing, card treatment and one restrained academic information block.

## Do not implement
- real homepage
- header/navigation/mobile drawer/footer
- About/Academic/Teacher/Staff pages
- notices/news/events
- results/routine/gallery/admission/downloads/contact page
- Frappe/backend/database/auth/payment/SMS

## Required self-check
- preview renders;
- no obvious broken layout/horizontal overflow;
- coherent typography and spacing;
- restrained gold and usable contrast;
- reusable components, no unnecessary hard-coding;
- mobile remains usable;
- no unnecessary dependencies;
- no future modules accidentally implemented.

## Final report
Return implemented items, key files/components, dependencies added, what was actually verified, what could not be verified, and what was deliberately deferred. Stop after Stage 1 and await review.
