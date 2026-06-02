# CI/CD Pipeline

ERP Plus uses GitHub Actions, GitHub Branch Protection Rules, and Taiga as its integrated delivery workflow.

---

## Purpose

The CI/CD pipeline guarantees:

- code quality
- automated testing
- security validation
- architectural compliance
- deployment readiness
- traceability between Taiga and GitHub

---

## Core Principle

Every change must originate from a tracked work item.

Work items are managed in Taiga and implemented through GitHub.

The CI/CD pipeline acts as the validation layer between development and deployment.

---

## Workflow Overview

```txt
Epic (optional)
        ↓
User Story (Taiga)
        ↓
Task (Taiga)
        ↓
Branch
        ↓
Commits
        ↓
Pull Request → develop
        ↓
CI Validation
        ↓
Review
        ↓
Merge into develop
        ↓
Ready for Test
        ↓
Pull Request → main
        ↓
Release Validation
        ↓
Merge into main
        ↓
Done
        ↓
Deploy
```

---

## Relationship Between Taiga and GitHub

### Planning Layer

Taiga manages:

- Epics
- User Stories
- Tasks
- Issues
- Sprints

GitHub manages:

- Source code
- Pull Requests
- CI/CD
- Releases

---

## Branch Strategy

Internal contributors create branches linked to a Taiga User Story.

Example:

```bash
feature/TG-123-user-invitations
```

Documentation examples:

```bash
docs/TG-33-localizacion-onboarding
```

Community contributors may use:

```bash
feature/user-invitations
docs/update-installation-guide
```

---

## Commit Traceability

All commits related to a Taiga User Story should reference its identifier.

Example:

```bash
feat(users): add invitation workflow TG-123

docs(workflow): update branch strategy TG-33
```

---

## Pull Request Lifecycle

### Pull Request to develop

Purpose:

- integration
- validation
- QA readiness

Flow:

```txt
Branch
   ↓
PR → develop
   ↓
CI
   ↓
Review
   ↓
Merge
```

After merge:

- User Story is moved manually to:

```txt
Ready for Test
```

inside Taiga.

---

### Pull Request to main

Purpose:

- release
- production delivery

Flow:

```txt
develop
   ↓
PR → main
   ↓
Release Validation
   ↓
Merge
```

After merge:

- User Story is moved manually to:

```txt
Done
```

inside Taiga.

---

## CI Validation Stages

Every Pull Request must pass:

### Rubocop

Checks:

- style consistency
- linting rules

---

### RSpec

Checks:

- unit tests
- integration tests
- feature tests

---

### Brakeman

Checks:

- Rails security issues
- common vulnerabilities

---

### Build Validation

Ensures:

- application boots correctly
- dependencies are valid
- deployment artifacts can be generated

---

## Branch Behavior

### develop

Purpose:

```txt
Integration Branch
```

Characteristics:

- accepts feature merges
- CI validation required
- no production deployments

---

### main

Purpose:

```txt
Production Branch
```

Characteristics:

- release source
- protected branch
- production deployments originate here

---

## Sprint Integration

ERP Plus uses:

```txt
2-week sprints
```

managed in Taiga.

During a sprint:

- User Stories are planned
- Tasks are assigned
- GitHub work is linked back to Taiga items

---

## Issues Workflow

External feedback is managed through Taiga Issues.

Examples:

- bug reports
- feature requests
- client feedback
- operational incidents

Issues may generate:

```txt
Issue
   ↓
User Story
   ↓
Task
   ↓
Implementation
```

---

## Definition of Ready

Before implementation:

- User Story exists
- scope is clear
- engine ownership is defined
- acceptance criteria are defined

---

## Definition of Done

A change is considered complete only when:

- implementation finished
- tests added or updated
- CI passes
- review approved
- merged into main
- User Story moved to Done

---

## Governance Rule

No production change may bypass:

```txt
Taiga
→ GitHub PR
→ CI
→ Review
→ main
```

---

## Summary

The ERP Plus delivery pipeline is built around:

```txt
Taiga → GitHub → CI → Review → Release → Deploy
```

This provides:

- traceability
- predictable releases
- controlled system evolution
- auditability across the platform
