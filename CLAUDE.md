# CLAUDE.md

Minimal agent workflow. Optimize for speed; keep everything small.

## Workflow

```text
planner  →  dev  →  pr  →  human
```

1. **planner** (`.claude/agents/planner.md`) turns a request into small tickets in `docs/backlog/`.
2. **dev** (`.claude/agents/dev.md`) implements tickets with minimal tests.
3. **pr** (`.claude/agents/pr.md`) runs the checks and opens the pull request. The PR description is the only report.

For a tiny change, skip the planner and go straight to dev.

## Context

Read only what the task needs:

- `docs/architecture.md` – goal, stack, structure, constraints, decisions
- `docs/backlog/` – tickets

## Rules

- Simplest solution that meets the acceptance criteria. No speculative features.
- Tests cover acceptance criteria and core logic only. No coverage targets.
- Never commit secrets or credentials.
- Keep `docs/architecture.md` true: update it when the stack or structure changes.
- No separate reports. Everything worth saying goes into the PR description.
