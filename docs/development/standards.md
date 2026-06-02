# Engineering Standards (ERP Plus)

This document defines the engineering standards used across ERP Plus.

These standards apply to:

- platform maintainers
- internal contributors
- community contributors

---

## Core Principle

Every contribution must preserve:

- architectural boundaries
- engine ownership
- multi-tenancy safety
- traceability
- platform maintainability

---

## Engineering Values

ERP Plus prioritizes:

```txt
Clarity
Consistency
Traceability
Isolation
Maintainability
```

Over:

```txt
Complexity
Premature Optimization
Hidden Dependencies
```

---

## Work Tracking

ERP Plus uses:

```txt
Taiga
+
GitHub
```

for planning and execution.

Internal development work is tracked through:

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
Merge
```

---

## Traceability

Every internal contribution should be traceable back to a Taiga work item.

Examples:

```txt
TG-123
TG-245
TG-387
```

This identifier should appear in:

- branch names
- commit history
- Pull Requests

---

## Branch Naming

### Internal Contributors

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

Examples:

```bash
feature/user-invitations

fix/stock-calculation

docs/improve-installation-guide
```

---

## Commit Standards

ERP Plus follows Conventional Commits.

Examples:

```txt
feat(accounts): add invitation workflow

fix(inventory): resolve stock calculation

docs(workflow): update branch strategy
```

---

### Internal Commit Traceability

Internal contributors should reference the related work item.

Examples:

```txt
feat(accounts): add invitation workflow TG-123

fix(inventory): stock correction TG-245

docs(workflow): update standards TG-33
```

---

## Pull Requests

All contributions must go through Pull Requests.

Direct pushes to protected branches are prohibited.

See:

```txt
development/pr-standard.md
```

---

## Testing

Every contribution must be validated appropriately.

Minimum expectations:

| Change Type         | Validation           |
| ------------------- | -------------------- |
| Documentation       | Manual Review        |
| Feature             | Feature Testing      |
| Domain Logic        | Unit Tests           |
| Engine Changes      | Engine Tests         |
| Multi-Tenancy Logic | Isolation Validation |

See:

```txt
development/testing.md
```

---

## Architecture Rules

ERP Plus follows a Modular Monolith architecture.

Business capabilities are organized into Rails Engines.

Examples:

```txt
erp_core
erp_accounts
erp_users
erp_workers
erp_inventory
```

---

## Engine Isolation

Every engine should:

- own its domain
- expose explicit interfaces
- remain independently testable
- avoid hidden coupling

---

## Forbidden Practices

Do not:

- access internal engine implementation directly
- create circular dependencies
- bypass engine contracts
- duplicate domain logic across engines

---

## Multi-Tenancy Standards

Features affecting account data must preserve:

- tenant isolation
- authorization boundaries
- scoped access

Cross-account data access is prohibited unless explicitly authorized.

---

## Documentation Standards

Documentation is part of the product.

Documentation should be updated whenever:

- architecture changes
- workflows change
- contributor expectations change
- operational procedures change

---

## Security Standards

Never commit:

```txt
.env
credentials
master.key
production secrets
private certificates
```

If a secret is exposed:

```txt
Rotate
Revoke
Document
Review
```

---

## CI Standards

Every Pull Request must pass:

```txt
RSpec
Rubocop
Brakeman
Build Validation
```

A failing pipeline blocks merge.

---

## Internal vs Community Contributions

| Capability           | Internal | Community |
| -------------------- | -------- | --------- |
| Taiga Access         | Yes      | No        |
| User Stories         | Yes      | No        |
| Tasks                | Yes      | No        |
| GitHub Issues        | Yes      | Yes       |
| Pull Requests        | Yes      | Yes       |
| Code Review Required | Yes      | Yes       |

---

## Definition of Quality

A contribution is considered high quality when it:

- solves the intended problem
- respects architecture boundaries
- includes appropriate validation
- remains maintainable
- preserves traceability

---

## Mental Model

```txt
Taiga
↓
Branch
↓
Commit
↓
Pull Request
↓
Testing
↓
Review
↓
Merge
↓
Deploy
```

---

## Final Definition

> Engineering standards in ERP Plus exist to ensure that every contribution remains traceable, testable, maintainable, and aligned with the platform architecture.
