# EduSite Project Control — START HERE

This repository is the canonical control plane and permanent project memory for EduSite.

## Authority
1. The latest **VERIFIED/MERGED repository state** overrides chat memory or agent assumptions.
2. Chat history is disposable; GitHub state is authoritative.
3. No implementation work may begin in a new session until the mandatory context below has been read.
4. Existing/legacy repositories are off-limits unless the project owner explicitly authorizes touching a specific repository.

## Mandatory read order for every new AI session
1. `PROJECT_STATE.yaml`
2. `CURRENT_STATE.md`
3. `PROJECT_CHARTER.md`
4. `ARCHITECTURE.md`
5. `AI_EXECUTION_POLICY.md`
6. Relevant files in `adr/`
7. Relevant specification in `specs/`
8. Active task in `tasks/`
9. Latest relevant file in `reviews/`
10. Relevant code repository state/commit/PR, if a code repository exists

After reading, report only:
- last verified task
- current task/status
- current milestone
- next action
- blockers/uncertainties

Then proceed.

## Non-negotiable completion rule
A task is not complete merely because code was implemented. It closes only after:
- implementation is complete;
- required verification passes;
- verified code is merged to the stable branch where applicable;
- task status is updated;
- `PROJECT_STATE.yaml` is updated;
- `CURRENT_STATE.md` is updated;
- verification/review evidence is recorded;
- the next action is identified.

No new task starts while canonical state is unsynchronized.
