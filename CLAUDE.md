# CLAUDE.md

Minimal agent workflow. Optimize for speed; keep everything small.

## Workflow

```text
planner  →  dev  →  pr  →  human
```

1. **planner** (`.claude/agents/planner.md`) plans a request as features of 3 to 10 tickets, one folder per feature in `docs/backlog/`.
2. **dev** (`.claude/agents/dev.md`) implements one feature ticket by ticket with minimal tests on its own branch and proposes the pull request after the last ticket.
3. **pr** (`.claude/agents/pr.md`) runs only when a pull request is requested: it runs the checks, pushes the branch, and opens or updates the pull request. The PR description is the only report: progress, roadmap, cost estimate and critical security risks.

**Small changes** skip the planner: dev writes a single ticket in `docs/hotfix/NN-slug.md` and works on branch `hotfix/NN-slug`.

## Branches and commits

| Work | Branch | Commit |
|---|---|---|
| Feature | `feature/NN-slug` | `NN-MM: <ticket title>` |
| Hotfix | `hotfix/NN-slug` | `hotfix NN: <title>` |

Never commit to or push `main` directly. Pull requests go into `main`.

## Context

Read only what the task needs:

- `docs/architecture.md` – goal, stack, structure, constraints, roadmap, decisions
- `docs/backlog/NN-slug/` – features (dev: only its own feature folder)
- `docs/hotfix/NN-slug.md` – small changes

## Autonomy

Work as autonomously as possible. Do not stop to ask the human during planning or implementation.

- When something is unclear, choose the most reasonable option, note it under **Open questions** in the `feature.md` or hotfix file as `question → assumption taken`, and continue.
- The human answers open questions in the pull request review. dev then records each answer as `question → answer`, adds tickets for changes to the same folder, implements them on the same branch, and proposes to update the pull request.
- Stop only when work is impossible without the human, for example missing credentials or access.

## Rules

- Simplest solution that meets the acceptance criteria. No speculative features.
- Tests cover acceptance criteria and core logic only. No coverage targets.
- Never commit secrets or credentials.
- Keep `docs/architecture.md` true: update it when the stack or structure changes.
- No separate reports. Everything worth saying goes into the PR description.
