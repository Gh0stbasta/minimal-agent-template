# CLAUDE.md

# Purpose

This repository uses a specialized multi-agent software factory.

The repository itself is the source of truth.

Documentation, architecture, backlog, reports, and implementation artifacts are expected to remain synchronized.

Conversation history is temporary.

Repository files are durable context.

---

# Factory Model

Work is performed by specialized agents.

Typical flow:

```text
Business
    ↓
Architect
    ↓
Development
    ↓
Reviewer
    ↓
Test
    ↓
Security (optional)
    ↓
PR
    ↓
Business
    ↓
Human
```

An Orchestrator Agent coordinates agent selection and workflow progression.

The workflow is adaptive and model-driven.

Agent activation order may vary based on evidence, findings, risks, and project needs.

---

# Agent Authority

Agent definitions located under:

```text
.claude/agents/
```

are authoritative for agent behavior.

Each agent defines:

- Responsibilities
- Allowed actions
- Restricted actions
- Context access
- Reporting requirements
- Output ownership

Agents should operate only within their assigned responsibilities.

Do not assume responsibilities owned by another agent.

---

# Human Authority

Human intent is authoritative.

Read human-owned project context from:

```text
.human/
```

Human-owned files define:

- Vision
- Goals
- Priorities
- Constraints
- Risk tolerance
- Cost expectations
- Ethics

Agents may interpret human intent but must not silently rewrite it.

---

# Repository Discovery

Before making decisions:

1. Understand the repository structure.
2. Read relevant documentation.
3. Review current project status.
4. Review existing architecture and backlog information when applicable.
5. Review relevant reports for the current mission.

Do not make implementation decisions without understanding the relevant repository context.

---

# Documentation Philosophy

Documentation is part of the product.

Documentation should describe the current reality of the repository.

Keep documentation synchronized with implementation.

Do not document planned behavior as if it already exists.

Prefer repository files over conversation history when determining system state.

---

# Context Philosophy

Context should remain intentionally limited.

Read only the information required for the current mission.

Avoid loading unrelated features, reports, code, or documentation.

Prefer focused context over large context windows.

Agent reports are the preferred mechanism for transferring information between agents.

---

# Engineering Principles

Prefer:

- Simplicity
- Correctness
- Maintainability
- Security
- Reliability
- Operability
- Cost awareness
- Observability
- Testability
- Reversibility

Avoid:

- Overengineering
- Premature abstraction
- Unnecessary dependencies
- Hidden complexity
- Scope expansion without justification

Always prefer the simplest solution that satisfies the requirements.

---

# Architecture Principles

Architecture should evolve intentionally.

Architecture complexity must be justified by a requirement.

Favor:

```text
Requirement
    ↓
Design
    ↓
Implementation
```

over:

```text
Technology
    ↓
Problem Search
```

Document significant decisions.

Surface trade-offs.

Preserve traceability between goals, architecture, implementation, testing, and delivery.

---

# Security Principles

Security concerns should be documented and made visible.

Do not:

- Expose secrets
- Commit credentials
- Hide findings
- Ignore security risks

Security findings, limitations, and recommendations should be recorded through the appropriate project artifacts.

---

# Operational Principles

Prefer safe and reversible changes.

Before destructive work:

- Assess impact
- Assess risk
- Define rollback options

Avoid unnecessary changes to:

```text
production systems
external systems
shared infrastructure
credentials
access controls
```

unless explicitly authorized.

---

# Reporting

Reports are the primary communication mechanism between agents.

Reports should be:

- Clear
- Concise
- Evidence-based
- Traceable
- Actionable

Do not rely on conversation history as the primary handover mechanism.

---

# Source of Truth

When determining repository state, prefer:

```text
Current Documentation
↓
Current Reports
↓
Current Backlog
↓
Current Implementation
↓
Conversation History
```

Repository artifacts outweigh temporary chat context.

---

# Core Principle

Build sustainable systems through specialized responsibilities, clear ownership, limited context, documented decisions, and evidence-based progression.

Favor clarity over cleverness.

Favor maintainability over novelty.

Favor documented knowledge over implicit knowledge.
