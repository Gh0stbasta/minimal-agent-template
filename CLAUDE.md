# CLAUDE.md

Minimal agent workflow. Optimize for speed; keep everything small.

## Workflow

```text
planner  →  dev  →  pr  →  human
```

1. **planner** (`.claude/agents/planner.md`) plans a request as features of 3 to 10 tickets, one folder per feature in `docs/backlog/`.
2. **dev** (`.claude/agents/dev.md`) implements one feature ticket by ticket with minimal tests, reading only its own feature folder, and proposes the pull request after the last ticket.
3. **pr** (`.claude/agents/pr.md`) runs only when a pull request is requested: it runs the checks and opens one pull request per feature. The PR description is the only report: progress, roadmap, cost estimate and critical security risks.

For a tiny change, skip the planner and go straight to dev.

## Context

Read only what the task needs:

- `docs/architecture.md` – goal, stack, structure, constraints, roadmap, decisions
- `docs/backlog/NN-feature/` – the feature being worked on (not the other features)

## Rules

- Simplest solution that meets the acceptance criteria. No speculative features.
- Tests cover acceptance criteria and core logic only. No coverage targets.
- Never commit secrets or credentials.
- Keep `docs/architecture.md` true: update it when the stack or structure changes.
- No separate reports. Everything worth saying goes into the PR description.
