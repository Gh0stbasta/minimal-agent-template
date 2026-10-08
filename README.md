# Minimal Agent Template

A lean template for building on AWS with three Claude Code agents. Built for speed: small tickets, minimal tests, one report per pull request.

```text
planner  →  dev  →  pr  →  human
```

| Agent | Does | Output |
|---|---|---|
| `planner` | Plans a request as features of 3–10 tickets | `docs/backlog/NN-feature/` |
| `dev` | Implements one feature ticket by ticket with minimal tests, then proposes the PR | Code, tests, one commit per ticket |
| `pr` | Only on request: runs the checks and opens one PR per feature | PR description (the only report): progress bars, upcoming features, cost per day and month for 5 and 5,000 users, critical security risks |

For tiny changes, skip the planner.

## Structure

```text
CLAUDE.md               rules for all agents
.claude/agents/         planner, dev, pr
docs/architecture.md    goal, stack, structure, constraints, roadmap, decisions
docs/backlog/           one folder per feature: feature.md + tickets (format: 00-template/)
app/backend/            backend
app/frontend/           frontend
infra/                  AWS CDK app (TypeScript)
.github/workflows/      pr.yml (checks), deploy.yml (cdk deploy on main)
```

## CI/CD

- `pr.yml`: lint, test and build for `app/backend`, `app/frontend` and `infra`, then `cdk synth`. Packages without a `package.json` are skipped.
- `deploy.yml`: on push to `main`, the same checks, then `cdk deploy --all` to `eu-central-1`.

Deployment needs:

1. The repository secret `AWS_ROLE_ARN`: an IAM role that trusts GitHub OIDC for this repository.
2. A one-time `npx cdk bootstrap` of the target account and region.

## Getting Started

1. Create a repository from this template.
2. Fill in `docs/architecture.md`, including the roadmap.
3. Ask the `planner` to plan features, let `dev` implement one feature, and accept its proposal to have `pr` open the pull request.
4. Review and merge.
