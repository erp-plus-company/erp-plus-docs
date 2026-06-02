# Pull Request Standard (ERP Plus)

This document defines the **official Pull Request contract** for ERP Plus.

Every contributor MUST follow this standard to ensure consistency, safety, and scalability across all engines.

---

## Core Principle

A Pull Request is not just a code change.

It is:

> a controlled modification inside a bounded engine that must respect architecture, multi-tenancy, and system governance.

---

## PR Scope Rules

### Allowed scope

A PR MUST belong to:

- a single engine (preferred)
- or a clearly defined cross-engine change (exception only)

---

### Forbidden scope

A PR must NOT:

- modify multiple engines without justification
- mix infrastructure + business logic randomly
- bypass engine boundaries
- introduce hidden dependencies

---

## PR Size Rule

PRs MUST be:

- small
- focused
- reviewable in < 30 minutes

If a PR is too large:

> split it before review

---

## PR Structure (Required)

Every PR MUST include:

```txt
Summary
Type of Change
Related Engine(s)
Changes Introduced
Tests Added/Updated
Migration Notes (if any)
Breaking Changes (if any)
Deployment Notes
```

---

## Taiga Traceability

Internal Pull Requests must reference the related User Story.

Examples:

```txt
TG-123
TG-88
TG-33
```

Branch example:

```bash
feature/TG-123-user-invitations
```

Commit example:

```bash
feat(accounts): add invitation workflow TG-123
```

---

## Status Management

ERP Plus currently uses manual state transitions inside Taiga.

The expected operational flow is:

```txt
Task
 ↓
Implementation
 ↓
Pull Request
 ↓
Merge to develop
 ↓
Ready For Test
 ↓
Validation
 ↓
Merge to main
 ↓
Done
```

Neither commits nor Pull Requests automatically change Taiga states.

Taiga remains the authoritative source for work tracking.

---

## Validation Requirements

Before requesting review:

### The PR MUST:

- pass CI pipeline
- pass RSpec tests
- pass Rubocop
- pass Brakeman security scan
- respect engine isolation rules

---

## Testing Requirements

- feature changes → feature specs required
- domain logic → unit tests required
- engine changes → engine-specific tests required

---

## Engine Awareness Rule

Every PR MUST clearly declare:

- which engine(s) are affected
- whether core system is impacted
- whether multi-tenancy is affected

---

## Cross-Engine Rules

Cross-engine changes are allowed ONLY if:

- interaction is through public services
- no internal engine logic is accessed directly
- contracts are explicitly defined

---

## Commit Traceability

Every PR SHOULD map cleanly to:

- commits
- feature branch
- engine scope

---

## Review Requirements

A PR is NOT valid until:

- at least 1 approval (2 for core changes)
- CI is green
- no security issues detected

---

## Merge Rules

Only maintainers can merge into:

- develop
- main

All merges MUST:

- preserve engine boundaries
- not break multi-tenancy
- not degrade CI health

---

## Definition of Done

A PR is DONE when:

- feature works
- tests exist
- CI passes
- documentation updated (if needed)
- no architecture rules violated

---

## Mental Model

```bash
Feature → Engine → PR → CI → Review → Merge → Deploy
```

---

## Summary

> A PR in ERP Plus is a controlled architectural unit, not just a code change.
