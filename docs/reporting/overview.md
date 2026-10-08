# 🧭 Project Dashboard

> Snapshot of **{{DATE}}**. Generated automatically from repository artifacts.

---

# 📌 Executive Summary

| | |
|---|---|
| **Project Health** | {{PROJECT_HEALTH}} |
| **Current Phase** | {{CURRENT_PHASE}} |
| **Current Focus** | {{CURRENT_FOCUS}} |
| **Biggest Blocker** | {{BIGGEST_BLOCKER}} |
| **Recommended Next Action** | {{NEXT_ACTION}} |

---

# 📈 Progress

```text
Overall Progress  ████████████████░░░░ {{OVERALL_PROGRESS}}%
Current Release   ████████████████░░░░ {{RELEASE_PROGRESS}}%
Backlog           █████████░░░░░░░░░░░ {{BACKLOG_PROGRESS}}%
Technical Debt    ███░░░░░░░░░░░░░░░░░ {{DEBT_PROGRESS}}%
```

✅ Completed: **{{DONE_COUNT}}**
🚧 In Progress: **{{IN_PROGRESS_COUNT}}**
📋 Open: **{{OPEN_COUNT}}**

---

# 🗺 Roadmap Status

| Milestone | Status | Progress |
|------------|------------|------------|
| {{MILESTONE_1}} | {{STATUS}} | {{PROGRESS}} |
| {{MILESTONE_2}} | {{STATUS}} | {{PROGRESS}} |
| {{MILESTONE_3}} | {{STATUS}} | {{PROGRESS}} |

---

# 🧩 Feature Status

| ✅ Delivered | 🚧 In Progress | 📋 Planned |
|---|---|---|
| {{FEATURE}} | {{FEATURE}} | {{FEATURE}} |
| {{FEATURE}} | {{FEATURE}} | {{FEATURE}} |
| {{FEATURE}} | {{FEATURE}} | {{FEATURE}} |

---

## 🧭 Current Mission

**Objective:** Complete and validate the currently active feature.

**Current assessment:** Development is complete. One architecture deviation requires independent review.

**Active agent:** Reviewer Agent

**Reason:** Validate implementation quality, scope compliance, and the documented deviation before testing.

**Next expected outcome:** Rework request, architecture assessment, or handover to testing.

---

# 🎫 Backlog Overview

| Category | Open | In Progress | Done |
|-----------|----------|----------|----------|
| Infrastructure | | | |
| Backend | | | |
| Frontend | | | |
| Security | | | |
| Operations | | | |
| Analytics | | | |
| Integrations | | | |
| AI | | | |

---

# 🚨 Open Risks

| Risk | Impact | Mitigation |
|----------|----------|----------|
| {{RISK}} | {{IMPACT}} | {{MITIGATION}} |
| {{RISK}} | {{IMPACT}} | {{MITIGATION}} |
| {{RISK}} | {{IMPACT}} | {{MITIGATION}} |

---

# 💰 Cost Overview

| Category | Current | Budget | Status |
|-----------|----------|----------|----------|
| Infrastructure | | | |
| AI Services | | | |
| Third-Party Services | | | |
| Total | | | |

### Cost Health

🟢 Within Budget

OR

🟡 Monitoring Required

OR

🔴 Budget Risk

### Cost Notes

{{COST_SUMMARY}}

---

# 🧱 Technical Debt

| Severity | Count | Summary |
|-----------|----------|----------|
| 🚨 High | | |
| ⚠ Medium | | |
| ✅ Low | | |

### Top Technical Debt Items

1. {{ITEM}}
2. {{ITEM}}
3. {{ITEM}}

---

# 🔐 Security Status

## Overall Security Health

🟢 Healthy

OR

🟡 Review Required

OR

🔴 Immediate Action Required

### Security Findings

- {{FINDING}}
- {{FINDING}}
- {{FINDING}}

### Security Improvements

- {{IMPROVEMENT}}
- {{IMPROVEMENT}}

---

# 🏛 Architecture Health

| Metric | Value |
|----------|----------|
| ADRs Accepted | |
| ADRs Pending | |
| Open Risks | |
| Critical Dependencies | |

### Current Architecture Concerns

- {{CONCERN}}
- {{CONCERN}}

### Recent Architecture Changes

- {{CHANGE}}
- {{CHANGE}}

---

# 🔥 Hotfix Overview

| Hotfix | Severity | Status |
|----------|----------|----------|
| {{HOTFIX}} | {{SEVERITY}} | {{STATUS}} |
| {{HOTFIX}} | {{SEVERITY}} | {{STATUS}} |

### Recent Production Issues

- {{ISSUE}}
- {{ISSUE}}

---

# 📊 Key Business Metrics

| Metric | Current | Target |
|----------|----------|----------|
| {{METRIC}} | {{VALUE}} | {{TARGET}} |
| {{METRIC}} | {{VALUE}} | {{TARGET}} |
| {{METRIC}} | {{VALUE}} | {{TARGET}} |

Source: `.human/businessGoal.md`

---

# 🎯 Recommended Next Actions

1. {{ACTION}}
2. {{ACTION}}
3. {{ACTION}}

---

# ✅ Decisions Needed

| Decision | Priority |
|------------|------------|
| {{DECISION}} | High |
| {{DECISION}} | Medium |
| {{DECISION}} | Low |

---

# 📦 Recent Deliveries

### Completed Since Last Report

- {{ITEM}}
- {{ITEM}}
- {{ITEM}}

### Upcoming Deliveries

- {{ITEM}}
- {{ITEM}}
- {{ITEM}}

---

# ℹ About This Dashboard

### Data Sources

Generated from:

- docs/backlog/
- docs/hotfix/
- docs/roadmap.md
- docs/architecture.md
- docs/security.md
- docs/technical-debt.md
- .human/*
- Git history
- CI/CD pipelines

### Generation Rules

- Completed tickets contribute to progress.
- Open risks affect project health.
- Technical debt affects architecture health.
- Cost metrics are compared against cost-policy.md.
- Business metrics are compared against businessGoal.md.
- Hotfixes influence operational health.
- Security findings influence security status.
- Architecture decisions influence architecture health.

### Refresh Policy

This dashboard should be regenerated whenever:

- A backlog ticket is completed
- A hotfix is closed
- Roadmap status changes
- Technical debt is updated
- Architecture changes
- Security findings change
- Cost metrics significantly change
