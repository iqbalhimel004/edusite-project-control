# Backend Specification

## Planned foundation
- Frappe Framework
- ERPNext
- Frappe Education
- EduSite BD custom app

## Reuse-first rule
Use built-in capabilities where they satisfy requirements. Avoid recreating student, guardian, attendance, admission, fee, assessment and similar core concepts without evidence of a real gap.

## Bangladesh custom scope candidates
- Class VI–X local structures
- section/shift/group
- Bangladesh examination/result rules
- marks/grades/GPA
- report cards/tabulation
- promotion logic
- local reports
- SMS provider integration
- bKash/Nagad/SSLCommerz or other justified payment integration

## Isolation
Prefer per-school Frappe site/database isolation under shared infrastructure where operationally appropriate.

## High-risk gates
Results, permissions, tenant isolation, database migrations, payments and production security require independent review/testing.
