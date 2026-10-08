# Minimal Agent Template

A lean template for building on AWS with three Claude Code agents. Built for speed: small tickets, minimal tests, one report per pull request.

```text
planner  →  dev  →  pr  →  human
```

| Agent | Does | Output |
|---|---|---|
| `planner` | Splits a request into small tickets | `docs/backlog/NNN-*.md` |
| `dev` | Implements tickets with minimal tests, one commit per ticket | Code, tests |
| `pr` | Runs the checks and opens the PR | PR description (the only report) |

For tiny changes, skip the planner.

## Structure

```text
CLAUDE.md               rules for all agents
.claude/agents/         planner, dev, pr
docs/architecture.md    goal, stack, structure, constraints, decisions
docs/backlog/           tickets (format: 000-template.md)
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
2. Fill in `docs/architecture.md`.
3. Ask the `planner` for tickets, let `dev` implement them, and have `pr` open the pull request.
4. Review and merge.
