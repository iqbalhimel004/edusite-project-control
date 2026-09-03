# ADR-002 — Custom Frontend + Frappe Backend
Status: Accepted

## Context
The product requires a highly customizable frontend but a reliable school-management backend. Building a complete management system through unconstrained vibe coding would create excessive risk and maintenance burden.

## Decision
Use a custom frontend (Next.js/React/TypeScript/Tailwind direction) and a backend based on Frappe Framework + ERPNext + Frappe Education, extended through a separate EduSite BD custom app for Bangladesh-specific requirements.

## Consequences
- frontend can evolve rapidly without rewriting core backend logic;
- existing mature school/ERP capabilities are reused;
- custom code focuses on genuine local gaps;
- upstream core changes are minimized.
