# Development Workflow

This document defines the official development workflow used across ERP Plus.

ERP Plus uses:

- GitHub for source control
- Taiga for project management
- Pull Requests for code review
- GitHub Actions for CI/CD

---

## Core Workflow

Development work follows this lifecycle:

```txt
Epic (optional)
 ↓
User Story
 ↓
Task
 ↓
Branch
 ↓
Implementation
 ↓
Pull Request
 ↓
Review
 ↓
Merge
```

---

## Internal Contributor Workflow

Internal contributors are members of ERP Plus and have access to both:

- GitHub
- Taiga

Workflow:

```txt
Epic (optional)
 ↓
User Story
 ↓
Task
 ↓
Branch
 ↓
Implementation
 ↓
Pull Request
 ↓
Review
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

---

## External Contributor Workflow

Community contributors do not have access to Taiga.

Workflow:

```txt
Fork
 ↓
Branch
 ↓
Implementation
 ↓
Pull Request
 ↓
Review
 ↓
Merge
```

---

## Branch Strategy

### Main Branches

| Branch  | Purpose     |
| ------- | ----------- |
| main    | Production  |
| develop | Integration |

---

### Branch Naming

#### Internal Contributors

Branches must reference the Taiga User Story.

Examples:

```bash
feature/TG-123-user-invitations

fix/TG-88-worker-retry

docs/TG-33-localizacion-onboarding
```

Allowed prefixes:

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

#### External Contributors

Community branches do not reference Taiga.

Examples:

```bash
feature/user-invitations

fix/worker-retry

docs/update-readme
```

---

## Commit Convention

ERP Plus uses Conventional Commits.

Examples:

```bash
feat(accounts): add invitation workflow TG-123

fix(workers): retry strategy TG-88

docs(workflow): update development workflow TG-33
```

Optional traceability tags may be included:

```bash
feat(accounts): add invitation workflow TG-123 #in-progress
```

---

### Important

Tags such as:

```txt
#in-progress
#ready-for-test
#done
```

are currently informational.

They provide traceability between GitHub and Taiga but do not automatically move Taiga objects between states.

State transitions remain manually managed inside Taiga.

---

## Pull Requests

All changes must go through Pull Requests.

Direct pushes to protected branches are forbidden.

---

## Merge Rules

A Pull Request can only be merged when:

- CI passes
- tests pass
- security checks pass
- review is approved

---

## State Management

Taiga remains the source of truth for work status.

Current operational flow:

```txt
Task
 ↓
Implementation
 ↓
Pull Request
 ↓
Merge to develop
 ↓
Manual transition → Ready For Test
 ↓
Validation
 ↓
Merge to main
 ↓
Manual transition → Done
```

---

## Related Documents

→ [Feature Lifecycle](../development/feature-lifecycle.md)

→ [Pull Request Standards](../development/pr-standard.md)

→ [Testing](../development/testing.md)

→ [Development Standards](../development/standards.md)
