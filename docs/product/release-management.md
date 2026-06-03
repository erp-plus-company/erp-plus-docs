# Release Management

ERP Plus uses a controlled release process to move validated work into production.

---

## Core Principle

No code reaches production directly.

Every release follows:

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

## Release Flow

```txt
User Story
   ↓
Task Completed
   ↓
Pull Request
   ↓
Merge into develop
   ↓
Validation
   ↓
Merge into main
   ↓
Production Release
```

---

## Branch Roles

### develop

Integration branch.

Contains:

- completed features
- validated work
- release candidates

---

### main

Production branch.

Contains:

- stable releases
- deployable code

---

## Status Transitions

### Development

When work begins:

```txt
In Progress
```

---

### Pull Request Created

When implementation is complete:

```txt
Ready for Test
```

---

### Validation Complete

After review and testing:

```txt
Ready for Release
```

---

### Production Deployment

After merge into main:

```txt
Done
```

---

## Release Requirements

Before merging into main:

- tests must pass
- CI must pass
- review must be approved
- documentation must be updated if required

---

## Production Release

A release may contain:

- multiple User Stories
- bug fixes
- technical improvements

---

## Emergency Releases

Critical fixes may use:

```txt
hotfix/TG-XXX-description
```

Emergency releases must still:

- pass CI
- be reviewed
- be documented

---

## Traceability

Every production change must be traceable back to:

```txt
Production Release
      ↓
Pull Request
      ↓
Branch
      ↓
User Story
      ↓
Issue (optional)
```

---

## Goal

Release management guarantees:

- predictable deployments
- auditability
- rollback capability
- production stability
