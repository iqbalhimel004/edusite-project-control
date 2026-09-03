# EduSite Architecture

## 1. High-level architecture

```text
Public School Website
Next.js / React / TypeScript / Tailwind
        |
        | shared documented API/data contracts
        v
Frappe Framework
+ ERPNext
+ Frappe Education
+ EduSite BD custom app
        |
        v
Per-school Frappe sites/databases on shared infrastructure where appropriate
        ^
        |
Future Android/mobile client uses the same backend/API contracts
```

The public website must never become the only place where essential school business logic or data access rules exist. This keeps SEO/server rendering strong on the web while preserving a clean path to future Android/mobile clients.

## 2. Frontend architecture
Approved direction:
- Next.js
- React
- TypeScript
- Tailwind CSS
- App Router when supported by the actual environment
- reusable components
- semantic theme/design tokens
- shadcn/ui only where genuinely useful
- Lucide icons where appropriate

### Data layering
```text
Web UI
  -> typed/platform-neutral domain models
  -> data-provider/service boundary
  -> mock provider (development)
  -> Frappe/API provider (future)

Future Android app
  -> mobile UI
  -> same documented API/auth/data contracts
```

UI must not directly depend on mock-data files. Business rules that must be shared across clients belong in the backend/domain contract rather than being hidden only in React components.

### SEO/rendering principle
Public, indexable school content should use server/static rendering where appropriate. Important public content must remain crawlable without depending unnecessarily on client-side JavaScript. Metadata, canonical URLs, sitemap/robots, structured data and stable URLs are first-class requirements rather than post-launch add-ons.

### Performance principle
Keep the public site server-first and JavaScript-light. Optimize media, fonts, caching and data fetching deliberately. Core Web Vitals and representative mobile measurements are release evidence, not visual guesses.

### White-label customization
A new school should eventually be configurable through:
- school name / short name
- logo / motto
- colors / semantic theme tokens
- photos / imagery
- address / contacts / social links
- EIIN and school information
- homepage section visibility
- homepage section ordering
- limited supported layout/section variants
- domain

Do not build a free-form drag-and-drop page builder unless a later decision explicitly changes this.

### Localization
Architecture should support a simple model such as:
```ts
type LocalizedString = {
  en: string;
  bn?: string;
};
```
Current demo may be English-first; typography/layout should remain Bangla-ready. If localized URLs are later introduced, canonical/hreflang strategy must be defined explicitly.

## 3. Public information architecture
- Home
- About
  - School Overview
  - History
  - Vision & Mission
  - Head Teacher's Message
  - Managing Committee
- Academics
  - Academic Information
  - Classes & Subjects
  - Class Routine
  - Academic Calendar
- Faculty & Staff
  - Teachers
  - Staff
- Students
  - Admission
  - Internal Examination Results
  - Downloads
- Updates
  - Notices
  - News
  - Events
- Media
  - Gallery
- Contact

## 4. Homepage direction
Target about 9–10 major visual sections. Likely groups:
- utility/header/navigation
- hero
- statistics/achievements
- latest notices
- head teacher message
- school introduction + academic highlights
- featured teachers
- latest news/events
- gallery/admission/contact grouping
- professional footer

Exact grouping may be refined based on visual evidence.

## 5. Results UX
Results mean **internal school examinations**.
Future lookup inputs:
- academic year
- examination
- class
- section
- roll/student identifier

Future output may include subject-wise marks, grade, GPA and print-friendly result presentation. Calculation logic is a high-risk module and must receive independent verification. Result calculation rules belong in backend/domain logic so web and future mobile clients consume the same truth.

## 6. Routine UX
Desktop and mobile may use different presentations of the same data:
- desktop: structured grid/table where appropriate
- mobile: day tabs and/or period cards

Do not solve mobile responsiveness by merely shrinking a desktop table.

## 7. Backend architecture
Use proven core capabilities from Frappe/ERPNext/Frappe Education where available. Keep upstream core changes minimal.

Bangladesh-specific features belong in a separate custom Frappe app, tentatively `edusite_bd`, including as needed:
- local class/section/shift/group structure
- Bangladesh-specific examination/result rules
- report cards / tabulation
- promotion logic
- local reporting
- SMS integration
- local payment integrations

API/auth/media contracts exposed to clients should be documented and designed for both web and future mobile use rather than tied to browser-only behavior.

## 8. Android/mobile readiness
The website is not the Android app, but the architecture must make the app straightforward later.

Principles:
- no DOM scraping as an app integration strategy;
- reuse the same Frappe/backend data and business rules;
- keep domain contracts platform-neutral where practical;
- use mobile-compatible authentication and file/media delivery when those systems are introduced;
- preserve stable deep-linkable URLs;
- leave room for push notifications and app-specific caching/offline behavior later;
- PWA support may be added when commercially useful, but it does not automatically replace a dedicated Android client.

Exact mobile framework is intentionally deferred. After the backend/API stabilizes, compare Expo/React Native and other justified options through an ADR.

## 9. Multi-school architecture
Long-term preference: Frappe multi-site / per-site database isolation on self-managed infrastructure when appropriate.

Frappe Cloud is optional, not mandatory.

## 10. Hosting resources currently available
- Hostinger Business hosting: candidate for public frontend where technically compatible.
- Heroku student credits: useful for development/staging/microservices, not default production Frappe hosting.
- Production backend likely moves to a VPS/self-hosted Frappe deployment after evidence-based sizing.
