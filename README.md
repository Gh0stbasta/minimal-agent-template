# Minimal Agent Template

A lean template for building on AWS with three Claude Code agents. Built for speed: small tickets, minimal tests, one report per pull request.

```text
planner  →  dev  →  pr  →  human
```

| Agent | Does | Output |
|---|---|---|
| `planner` | Plans a request as features of 3–10 tickets | `docs/backlog/NN-slug/` |
| `dev` | Implements one feature or hotfix on its own branch with minimal tests, then proposes the PR | Code, tests, one commit per ticket |
| `pr` | Only on request: runs the checks, pushes, opens or updates the PR | PR description (the only report): progress bars, upcoming features, cost per day and month for 5 and 5,000 users, critical security risks |

Small changes skip the planner: dev writes a hotfix in `docs/hotfix/` on branch `hotfix/NN-slug`. Features use `feature/NN-slug`. Nothing is committed to `main` directly.

Agents work autonomously: unclear points are recorded as `question → assumption` and answered by you in the PR review.

## Structure

```text
CLAUDE.md               rules for all agents
.devcontainer/          Node 24, AWS CLI, GitHub CLI
.claude/agents/         planner, dev, pr
docs/architecture.md    goal, stack, structure, constraints, roadmap, decisions
docs/backlog/           one folder per feature: feature.md + tickets (format: 00-template/)
docs/hotfix/            one file per small change (format: 00-template.md)
app/backend/            backend (npm package)
app/frontend/           frontend (npm package)
infra/                  AWS CDK app (TypeScript, npm package)
.github/workflows/      pr.yml (checks), deploy.yml (cdk deploy on main)
```

## CI/CD

- `pr.yml`: lint, test and build for `app/backend`, `app/frontend` and `infra`, then `cdk synth`. Packages without a `package.json` are skipped. Each package needs a committed `package-lock.json`.
- `deploy.yml`: on push to `main`, the same checks, then `cdk deploy --all` to `eu-central-1`.

Deployment needs:

1. The repository secret `AWS_ROLE_ARN`: an IAM role that trusts GitHub OIDC for this repository.
2. A one-time `npx cdk bootstrap` of the target account and region.

## Getting Started

1. Create a repository from this template.
2. Fill in `docs/architecture.md`, including the roadmap.
3. Ask the `planner` to plan features, let `dev` implement one feature, and accept its proposal to have `pr` open the pull request.
4. Answer the open questions in the review; dev implements the answers and pr updates the PR.
5. Merge.
