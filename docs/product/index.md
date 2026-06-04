# Product & Delivery Management

This section describes how ERP Plus plans, tracks, validates, and delivers work.

ERP Plus separates:

```txt
Planning
Implementation
Deployment
```

into dedicated systems.

---

## Core Principle

ERP Plus is not managed directly from GitHub.

Work begins in Taiga and moves through a controlled delivery workflow.

```txt
Taiga
  ↓
GitHub
  ↓
CI/CD
  ↓
Production
```

---

## Contents

### Roles Involved

Product delivery involves:

- Product Owners
- Scrum Masters
- Tech Leads
- Engineers
- QA Engineers

See:

→ [Roles and Responsibilities](../organization/roles-and-responsibilities.md)

### Taiga Workflow

How Epics, User Stories, Tasks, and Issues are managed.

→ [Taiga Workflow](../product/taiga-workflow.md)

---

### Sprint Process

How work is planned and executed during two-week iterations.

→ [Sprint Process](../product/sprint-process.md)

---

### Issue Management

How bugs, requests, and customer feedback are handled.

→ [Issue Management](../product/issue-management.md)

---

### Release Management

How completed work moves into production.

→ [Release Management](../product/release-management.md)

---

## Goal

This section is the source of truth for:

- planning
- prioritization
- execution
- validation
- releases
