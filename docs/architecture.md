# Architecture

Fill in the sections marked _TBD_ when starting a project. Keep this file short and current.

## Goal

_TBD: What problem does the product solve, and for whom?_

## Scope

- In: _TBD_
- Out: _TBD_

## Stack

| Part | Choice |
|---|---|
| Cloud | AWS (`eu-central-1`) |
| Infrastructure | AWS CDK (TypeScript) in `infra/` |
| Backend | _TBD_ in `app/backend/` |
| Frontend | _TBD_ in `app/frontend/` |
| CI/CD | GitHub Actions (`.github/workflows/`) |

## Structure

```text
app/backend/    backend code
app/frontend/   frontend code
infra/          CDK app (deploys everything)
docs/backlog/   tickets
```

## Constraints

_TBD: budget, compliance, data location, anything the agents must respect._

## Decisions

One line per significant decision: date, decision, reason.

- _none yet_
