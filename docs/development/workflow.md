# Development Workflow

This document defines the official development workflow used across ERP Plus.

ERP Plus uses:

- Taiga for product management
- GitHub for source control
- GitHub Actions for CI/CD
- Pull Requests for code review

---

## Workflow Types

ERP Plus supports two contribution models:

| Contributor Type      | Taiga Access | GitHub Access |
| --------------------- | ------------ | ------------- |
| ERP Plus Staff        | Yes          | Yes           |
| Community Contributor | No           | Yes           |

Because of this, some workflow rules differ depending on contributor type.

---

## ERP Plus Staff Workflow

All internal development starts in Taiga.

### Lifecycle

```txt
Epic
 └── User Story
        └── Task
               └── Branch
                      └── Pull Request
                             └── Merge
                                    └── Deploy
```

---

## Planning

Work is organized using:

- Epics
- User Stories
- Tasks
- Issues
- Sprints

Sprint duration:

```txt
2 weeks
```

User Stories may:

- belong to an Epic
- exist independently

---

## Branch Creation

Branches are created from a Taiga Task.

Branch format:

```txt
feature/TG-123-user-invitations
fix/TG-456-worker-retry
refactor/TG-789-engine-boundary
docs/TG-111-update-workflow
```

Pattern:

```txt
<type>/TG-<task-id>-<description>
```

---

## Commit Convention

ERP Plus uses Conventional Commits.

Examples:

```txt
feat(users): add invitation workflow

fix(workers): resolve retry issue

docs(system): update architecture guide
```

When linked to Taiga:

```txt
feat(users): add invitation workflow TG-123
```

or

```txt
feat(users): add invitation workflow [TG-123]
```

The exact format depends on Taiga integration requirements.

---

## Pull Request Flow

```txt
Task
  ↓
Branch
  ↓
Commit
  ↓
Pull Request
  ↓
Review
  ↓
Merge
```

Every Pull Request must reference:

- Taiga Task
- User Story
- Epic (if applicable)

---

## Synchronization

Taiga and GitHub are synchronized through webhooks.

The integration is expected to synchronize:

- Branches
- Commits
- Pull Requests
- Issues
- Task status
- User Story status
- Epic progress

---

## Community Contributor Workflow

Community contributors do not require Taiga access.

Workflow:

```txt
Issue
  ↓
Fork
  ↓
Branch
  ↓
Pull Request
  ↓
Review
  ↓
Merge
```

---

### Branch Naming

Community branches use:

```txt
feature/user-invitations

fix/login-validation

docs/update-installation-guide
```

No Taiga identifier is required.

---

### Pull Requests

Community Pull Requests should:

- explain the change
- reference GitHub Issues when applicable
- include tests when required
- update documentation when necessary

---

### Branch Types

Official branch prefixes:

```txt
feature/
fix/
refactor/
docs/
chore/
ci/
security/
```

---

## Main Branches

| Branch  | Purpose     |
| ------- | ----------- |
| main    | Production  |
| develop | Integration |

Direct pushes to protected branches are prohibited.

---

## Merge Requirements

A Pull Request may only be merged when:

- CI passes
- Tests pass
- Security checks pass
- Required reviews are approved

---

## CI Validation

CI validates:

- Rubocop
- RSpec
- Brakeman
- Build integrity

A Pull Request with failing CI cannot be merged.

---

## Related Documents

→ [Feature Lifecycle](../development/feature-lifecycle.md)

→ [Pull Request Standards](../development/pr-standard.md)

→ [Testing](../development/testing.md)

→ [Development Standards](../development/standards.md)

---

## Summary

ERP Plus development is governed by:

```txt
Taiga
   ↓
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
Review
   ↓
Merge
   ↓
Deploy
```

Community contributors follow a simplified GitHub-only workflow.
