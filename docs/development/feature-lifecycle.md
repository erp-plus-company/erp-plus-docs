# Feature Lifecycle (ERP Plus)

This document defines the complete lifecycle of a feature inside ERP Plus.

---

# Core Principle

A feature is not just code.

It is a controlled lifecycle managed through Taiga, GitHub, CI, and deployment workflows.

---

# Feature Lifecycle

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
Testing
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

# 1. Planning Phase

Work may begin from:

- Epic
- User Story
- Issue

User Stories may exist independently or belong to an Epic.

---

# 2. User Story

Every implementation must be associated with a User Story.

The User Story is the planning unit used by the team.

---

# 3. Task

Tasks are implementation units linked to a User Story.

Development work starts from a Task.

---

# 4. Branch Creation

Internal contributors create branches referencing the User Story.

Example:

```bash
feature/TG-123-user-invitations
```

---

# 5. Implementation

Rules:

- respect engine boundaries
- preserve multi-tenancy
- avoid hidden dependencies
- follow Rails conventions

---

# 6. Testing

Every feature must include appropriate tests.

Examples:

- unit tests
- feature tests
- engine-specific tests

```bash
bundle exec rspec
```

---

# 7. Pull Request

Every feature must be submitted through a Pull Request.

The Pull Request becomes the review unit.

---

# 8. CI Validation

CI validates:

- RSpec
- Rubocop
- Brakeman
- Build integrity

A feature cannot advance if CI fails.

---

# 9. Review

Review verifies:

- architecture compliance
- engine isolation
- multi-tenancy safety
- code quality

---

# 10. Merge to Develop

Once approved:

```txt
Feature Branch
 ↓
develop
```

At this point the User Story becomes:

```txt
Ready For Test
```

The transition is currently managed manually inside Taiga.

---

# 11. Validation

Functional validation occurs against develop.

The objective is to verify:

- acceptance criteria
- integrations
- regressions

---

# 12. Merge to Main

Validated changes are merged into:

```txt
main
```

---

# 13. Completion

After production approval:

```txt
Done
```

is set manually in Taiga.

---

# Sprint Model

ERP Plus uses two-week sprints.

Planning occurs at the User Story level.

Execution occurs at the Task level.

---

# Summary

```txt
Epic (optional)
 ↓
User Story
 ↓
Task
 ↓
Branch
 ↓
Code
 ↓
Tests
 ↓
PR
 ↓
CI
 ↓
Review
 ↓
develop
 ↓
Ready For Test
 ↓
main
 ↓
Done
```
