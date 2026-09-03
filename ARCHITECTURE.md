# EduSite Architecture

## 1. High-level architecture

```text
Public School Website
Next.js / React / TypeScript / Tailwind
        |
        | secure API integration later
        v
Frappe Framework
+ ERPNext
+ Frappe Education
+ EduSite BD custom app
        |
        v
Per-school Frappe sites/databases on shared infrastructure where appropriate
```

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
UI
  -> typed domain models
  -> data-provider interface
  -> mock provider (development)
  -> Frappe provider (future)
```

UI must not directly depend on mock-data files.

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
Current demo may be English-first; typography/layout should remain Bangla-ready.

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

Future output may include subject-wise marks, grade, GPA and print-friendly result presentation. Calculation logic is a high-risk module and must receive independent verification.

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

## 8. Multi-school architecture
Long-term preference: Frappe multi-site / per-site database isolation on self-managed infrastructure when appropriate.

Frappe Cloud is optional, not mandatory.

## 9. Hosting resources currently available
- Hostinger Business hosting: candidate for public frontend where technically compatible.
- Heroku student credits: useful for development/staging/microservices, not default production Frappe hosting.
- Production backend likely moves to a VPS/self-hosted Frappe deployment after evidence-based sizing.
