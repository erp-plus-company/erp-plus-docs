# Pull Request Standard (ERP Plus)

This document defines the official Pull Request contract for ERP Plus.

Every Pull Request must preserve:

- architectural boundaries
- multi-tenancy rules
- engine ownership
- traceability with Taiga

---

## Core Principle

A Pull Request is not merely a code change.

It is:

> the implementation artifact of a User Story tracked in Taiga and validated through review, testing, and CI.

---

## Relationship with Taiga

Every Pull Request MUST be associated with:

- a User Story (preferred)
- or an Issue (bug, support request, operational task)

Examples:

```txt
TG-123 User Invitations
TG-245 Inventory Adjustment Workflow
TG-387 Customer Reported Bug
```

---

## Traceability Requirements

Every Pull Request MUST provide traceability between:

```txt
Taiga
↓
Branch
↓
Commits
↓
Pull Request
↓
Merge
```

A reviewer must be able to identify:

- why the change exists
- which User Story requested it
- which engine is affected

---

## Branch Naming

### Internal Contributors

Branches created from Taiga work items:

```bash
feature/TG-123-user-invitations

bugfix/TG-245-stock-calculation

docs/TG-33-localizacion-onboarding
```

Allowed prefixes:

```txt
feature/
bugfix/
hotfix/
refactor/
docs/
chore/
ci/
security/
```

---

### Community Contributors

External contributors do not have access to Taiga.

Branches should follow:

```bash
feature/user-invitations

fix/stock-calculation

docs/improve-installation-guide
```

---

## Pull Request Scope

Preferred scope:

- one User Story
- one engine
- one objective

---

## Allowed Scope

A Pull Request MAY:

- modify a single engine
- update documentation
- introduce infrastructure improvements
- fix a bug

---

## Discouraged Scope

Avoid:

- mixing unrelated User Stories
- combining infrastructure and business features
- modifying multiple engines without justification

---

## Pull Request Structure

Every Pull Request MUST contain:

```txt
Summary

Related Work Item

Affected Engine(s)

Changes Introduced

Testing Performed

Documentation Updated

Deployment Notes

Breaking Changes (if any)
```

---

## Related Work Item

Examples:

```txt
Taiga User Story: TG-123

Taiga Issue: TG-387
```

Community contributions may use:

```txt
N/A (Community Contribution)
```

---

## Testing Requirements

Every Pull Request MUST include appropriate testing.

Examples:

| Change Type   | Required Validation |
| ------------- | ------------------- |
| Domain Logic  | Unit Tests          |
| User Workflow | Feature Specs       |
| Engine Change | Engine Test Suite   |
| Documentation | Manual Validation   |

---

## CI Requirements

The Pull Request MUST pass:

- RSpec
- Rubocop
- Brakeman
- CI pipeline

A failing pipeline blocks merge.

---

## Review Requirements

Standard Changes:

- 1 approval required

Core Architecture Changes:

- 2 approvals recommended

Review verifies:

- engine isolation
- architecture compliance
- multi-tenancy safety
- testing quality
- documentation impact

---

## State Progression

Taiga task state changes are performed manually.

Typical flow:

```txt
Task Created
↓
In Progress
↓
Ready For Review
↓
Pull Request Opened
↓
Ready For Test
↓
Done
```

---

## Merge Policy

### Feature Branch → Develop

When a Pull Request is merged into:

```txt
develop
```

the associated User Story should move to:

```txt
Ready For Test
```

after validation by the responsible reviewer.

---

### Develop → Main

When the feature reaches production through:

```txt
main
```

the associated User Story should move to:

```txt
Done
```

---

## Community Contributions

External contributors:

- do not require Taiga access
- use GitHub Issues and Pull Requests
- follow the same architecture and testing rules

Maintainers are responsible for linking accepted contributions to internal planning if necessary.

---

## Definition of Done

A Pull Request is considered complete when:

- implementation is finished
- tests pass
- CI passes
- review is approved
- documentation is updated when required
- architecture rules remain intact

---

## Mental Model

```txt
User Story
↓
Branch
↓
Commits
↓
Pull Request
↓
Review
↓
Testing
↓
Merge Develop
↓
Ready For Test
↓
Merge Main
↓
Done
```

---

## Final Definition

> A Pull Request in ERP Plus is a controlled implementation unit linked to a work item, validated through architecture review, testing, and CI before becoming part of the platform.
