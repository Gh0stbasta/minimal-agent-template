# Agent Factory Template

A template repository for an AI-driven software factory: specialized Claude Code agents take a project from business intent to a reviewed pull request.

The repository does not contain a product yet. It provides the structure, rules and templates. Copy it for a new project and fill it in.

---

## Core Idea

Instead of one AI doing everything, work is split into clearly separated roles.

Each agent has its own responsibility, may only change specific files, and hands over its results as a **report in the repository**, not through chat history.

The repository is the durable memory of the project.

```text
Business → Architect → Development → Reviewer → Test → (Security) → PR → Business → Human
```

An **Orchestrator** decides which agent acts next. The order is adaptive: if the Reviewer finds problems, work goes back to Development.

---

## Repository Structure

### `.human/` – Human Intent

Human-owned context. It is authoritative: agents may interpret it but must not silently rewrite it.

| File | Content |
|---|---|
| `vision.md` | Problem, target audience, MVP |
| `businessGoal.md` | Measurable business goals |
| `priorities.md` | What matters most when trade-offs are required |
| `constraints.md` | Technology and organizational constraints (cloud, languages, frameworks) |
| `risk.md` | Risk appetite and critical risks |
| `cost-policy.md` | Budgets and cost guardrails |
| `ethics.md` | Ethical principles and boundaries |
| `design.md` | User experience and visual identity |
| `usergroup.md` | User groups |
| `definition-of-done.md` | When work counts as complete |

### `.claude/agents/` – Agents

Agent definitions with frontmatter, registered by Claude Code as subagents. They are authoritative for agent behavior.

| Agent | Responsibility | Output |
|---|---|---|
| `orchestrator` | Coordinates the workflow and selects the next agent | Orchestration report |
| `business` | Evaluates business value, maintains roadmap and metrics | Feature requests, `docs/business-metrics.md` |
| `architect` | Designs the architecture, writes ADRs, creates feature packages | Feature package in `docs/backlog/<FEATURE>/` |
| `dev` | Implements the feature ticket by ticket, one commit per ticket | Code, development report |
| `reviewer` | Independently assesses the implementation; ready for testing, rework or blocked | Review report (does not modify code) |
| `test` | Independently validates the feature and its acceptance criteria | Test report |
| `security` | Scoped security assessment, only on explicit request | Security report |
| `pr` | Aggregates all reports into one PR package for human review | PR report |

Also under `.claude/`:

- `context/agent-registry.md` – when to use which agent
- `context/`, `rules/`, `skills/` – empty templates for project-specific context, rules and skills

### `docs/` – Current Project State

| Path | Content |
|---|---|
| `architecture.md` | Current architecture |
| `security.md` | Security posture |
| `technical-debt.md` | Known technical debt |
| `roadmap.md` | Planned product evolution |
| `business-metrics.md` | Business metrics and outcome tracking |
| `backlog/` | Tickets; one folder per feature package (`feature.md`, `feature-scope.md`, `feature-status.md`, tickets). Template: `ticket-template.md` |
| `feature-requests/` | Feature requests, organized into `proposed/`, `approved/` and `rejected/` |
| `hotfix/` | Hotfix template |
| `reporting/` | `overview.md` project dashboard; agent reports in subfolders such as `development/`, `review/`, `testing/` |

Report subfolders and `docs/decisions/` (ADRs) are created by the agents when they write their first output.

### `app/` and `infra/` – Implementation

- `app/frontend/` – frontend application
- `app/backend/` – backend application
- `infra/` – Terraform infrastructure

These folders currently contain only placeholder READMEs.

### `.github/workflows/` – CI/CD

- `pr.yml` – on pull requests: validates Terraform and builds frontend and backend. Never applies infrastructure.
- `deploy.yml` – on push to `main`: builds, applies Terraform on AWS via GitHub OIDC, verifies the deployed API and publishes the frontend to S3/CloudFront.

Steps are skipped until `infra/`, `app/frontend/` and `app/backend/` contain code. Deployment requires the `AWS_ROLE_ARN` repository secret.

### Other Files

- `CLAUDE.md` – factory-wide principles for all agents
- `.devcontainer/` – development container for VS Code and Codespaces

---

## Getting Started

1. Create a new repository from this template.
2. Fill in all files in `.human/`.
3. Ask the **Business** agent to derive feature requests and a roadmap.
4. Ask the **Architect** agent to design the architecture and create the first feature package.
5. Let the **Orchestrator** drive Development, Review, Test and (optionally) Security.
6. Review the PR prepared by the **PR** agent and merge it.

The Business agent then measures whether the expected outcomes were achieved.
