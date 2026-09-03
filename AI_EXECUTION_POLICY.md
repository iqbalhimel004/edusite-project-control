# AI Execution Policy

## Roles
### ChatGPT
Technical Lead, architect, planner, coordinator, independent reviewer, release/security gatekeeper and canonical-state maintainer.

### Codex
Default implementation engine because the user's ChatGPT K-12 teacher plan makes Codex available without additional monetary usage cost.

### Fable 5.1
Preferred specialist for premium frontend/UI/UX exploration and visual refinement while access is available.

### Hyperagent
High-capability specialist/second-opinion agent. User has approximately USD 3,000 of credit. Use for complex autonomous engineering, hard debugging, unfamiliar codebases or independent review when it materially improves reliability.

### Antigravity
Available at very high practical capacity through the user's Google AI Pro resources. Use for large autonomous tasks, parallel investigation or specialist work when it is the best fit.

### Zed.dev
Primary role is IDE/workspace/operator surface. The user has three student-pack accounts, each with roughly USD 10/month AI credit for one year. Use Zed AI selectively rather than creating redundant parallel implementation.

### Notion
Optional supplementary human-friendly dashboard/knowledge surface. It is **not** the canonical source of truth; GitHub remains authoritative.

## Agent-selection principle
Choose the best tool for the task, not the most expensive tool and not a single favorite tool.

Default pattern:
**one primary implementer + one independent reviewer only when justified.**

Do not ask several agents to independently implement the same routine feature.

## Reasoning-effort policy
Use the closest supported equivalent:
- Low: deterministic/simple edits
- Medium: default implementation
- High: complex multi-file work/integration
- XHigh: architecture, security, difficult debugging
- Max: exceptional release-critical problems only

Escalate based on evidence, not automatically.

## Prompt policy
Prompts must be compact, precise and bounded. Persistent context belongs in GitHub docs, not repeated in every prompt.

Typical coding prompt:
> Implement TASK-XXX. Read AGENTS.md and tasks/TASK-XXX.md. Work only on the specified branch/scope. Run the task's required checks. Report changed files, verification evidence and unresolved issues. Do not merge.

## Technical-lead autonomy
The Technical Lead may independently:
- reorder tasks;
- choose agent/model/reasoning level;
- reject or request rework;
- add tests/verification;
- improve workflows;
- revise architecture when materially better evidence appears.

Material architecture/strategy changes must be documented before implementation.
