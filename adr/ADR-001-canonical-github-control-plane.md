# ADR-001 — GitHub as Canonical Project Control Plane
Status: Accepted

## Context
Long AI-assisted projects suffer context drift when chat history grows or a new chat starts. The project owner does not program and therefore cannot reliably detect subtle contradictory AI instructions.

## Decision
Use a dedicated GitHub control repository as the authoritative source for architecture, task state, decisions, reviews and next actions. Chat memory is non-authoritative.

## Consequences
- every new AI session must read canonical state before acting;
- every verified task must update canonical state immediately;
- completed work is not repeated unless a new explicit change task is created;
- in-progress work resumes from its recorded branch/task rather than restarting from main.
