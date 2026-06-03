# Taiga Workflow

ERP Plus uses Taiga as its planning and product management platform.

GitHub is used for implementation.

---

## Planning Hierarchy

Work is organized using the following hierarchy:

```txt
Epic (optional)
    ↓
User Story
    ↓
Task
    ↓
Branch
    ↓
Pull Request
```

---

## Epics

Epics group large initiatives.

Examples:

- Multi-Tenant Foundation
- User Invitations
- Inventory MVP

An Epic may contain multiple User Stories.

User Stories may also exist without an Epic.

---

## User Stories

A User Story represents a deliverable business outcome.

Examples:

```txt
TG-123 User Invitations

TG-124 Account Switching

TG-125 Product Management
```

Every implementation branch is linked to a User Story.

---

## Tasks

Tasks represent implementation work.

A User Story may contain multiple Tasks.

Example:

```txt
TG-123 User Invitations

 ├── Backend Invitation Service
 ├── Invitation UI
 ├── Email Delivery
 └── Acceptance Testing
```

---

## Branch Mapping

Internal contributors create branches using:

```txt
feature/TG-123-user-invitations
```

Community contributors use:

```txt
feature/user-invitations
```

---

## GitHub Integration

Taiga is linked to GitHub through webhooks.

The integration provides:

- commit traceability
- pull request traceability
- repository visibility

State transitions remain controlled by the team workflow.

---

## Workflow Summary

```txt
Epic
  ↓
User Story
  ↓
Task
  ↓
Branch
  ↓
Pull Request
  ↓
Deploy
```
