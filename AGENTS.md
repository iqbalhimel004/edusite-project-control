# EduSite Agent Instructions

1. Read `START_HERE.md` first.
2. GitHub canonical state overrides chat memory and agent assumptions.
3. Read `PROJECT_STATE.yaml`, `CURRENT_STATE.md`, relevant ADR/spec and active task before working.
4. Work on one bounded task at a time.
5. Do not modify unrelated files or repositories.
6. Legacy/old repositories are off-limits unless explicitly authorized by the project owner for that specific repository/action.
7. Do not silently change accepted architecture. Material changes require an ADR/update before implementation.
8. Do not claim verification you did not perform.
9. "Implemented" is not "done". A task closes only after required verification, merge where applicable, and canonical-state updates.
10. Keep prompts and reports compact. Persistent context belongs in this repository.
11. During prototype development, use proportionate security; before production, enforce the production security gate.
12. Never start the next task while canonical state for the previous task is unsynchronized.
