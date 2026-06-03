# Testing Strategy (ERP Plus)

This document defines the official testing strategy for ERP Plus.

Testing exists to ensure:

- platform stability
- engine isolation
- multi-tenancy safety
- deployment confidence

---

# Core Principle

A User Story is not complete because code was written.

A User Story is complete only when:

- implementation works
- tests pass
- CI passes
- review is approved

---

# Testing Lifecycle

Testing is part of the feature lifecycle.

```txt
User Story
↓
Implementation
↓
Local Validation
↓
Pull Request
↓
CI Validation
↓
Review
↓
Ready For Test
↓
Done
```

---

# Responsibility

Every contributor is responsible for validating their work before opening a Pull Request.

This applies to:

- internal contributors
- community contributors
- maintainers

---

# Running the Test Suite

Run the complete suite:

```bash
bundle exec rspec
```

---

# Validation Layers

ERP Plus uses multiple validation layers.

---

## 1. Unit Tests

Validate:

- services
- models
- policies
- domain logic

Goal:

- verify business rules

Examples:

```txt
Account creation
Inventory calculations
Permission rules
```

---

## 2. Feature Tests

Validate complete user workflows.

Goal:

- ensure the application behaves correctly from the user's perspective

Examples:

```txt
User invitations
Inventory adjustments
Account onboarding
```

---

## 3. Engine Tests

Every engine owns its own behavior.

Examples:

```txt
erp_core
erp_accounts
erp_users
erp_workers
erp_inventory
```

Engine-specific functionality should be validated inside the engine that owns it.

---

# Multi-Tenancy Validation

Every feature affecting account data should validate:

- tenant isolation
- account scoping
- authorization boundaries

Examples:

```txt
Account A cannot access Account B data
Queries remain scoped
Policies enforce ownership
```

---

# Pull Request Validation

Before requesting review:

- tests must pass locally
- no known failing examples should exist
- CI should be expected to pass

---

# CI Validation

Every Pull Request is validated by CI.

Current validation includes:

```txt
RSpec
Rubocop
Brakeman
Build Validation
```

If CI fails:

```txt
The Pull Request is not eligible for merge.
```

---

# User Story Validation

A User Story should not move to:

```txt
Ready For Test
```

until:

- implementation is complete
- testing is complete
- Pull Request is approved
- CI is green

---

# Ready For Test

Ready For Test means:

```txt
Development Complete
+
Tests Passing
+
CI Passing
+
Review Approved
```

It does NOT mean:

```txt
Possibly Working
Needs Verification
Partially Tested
```

---

# Done

A User Story should move to:

```txt
Done
```

only after:

- successful merge into main
- deployment validation
- acceptance verification when applicable

---

# Community Contributions

Community contributors should:

- run tests when possible
- ensure their changes do not break existing behavior
- provide validation details in the Pull Request

Maintainers remain responsible for final verification.

---

# Minimum Testing Expectations

| Change Type        | Expected Validation           |
| ------------------ | ----------------------------- |
| Documentation      | Manual Review                 |
| Bug Fix            | Regression Test Preferred     |
| New Feature        | Feature Test Recommended      |
| Domain Logic       | Unit Tests Required           |
| Multi-Tenant Logic | Isolation Validation Required |
| Engine Changes     | Engine Tests Required         |

---

# Testing Philosophy

ERP Plus favors:

```txt
Reliable Tests
Over
Large Numbers of Tests
```

Tests should be:

- deterministic
- maintainable
- isolated
- meaningful

---

# Mental Model

```txt
Code
↓
Tests
↓
CI
↓
Review
↓
Ready For Test
↓
Production
```

---

# Final Definition

> Testing in ERP Plus is the validation process that transforms an implementation into a deployable and trustworthy feature.
