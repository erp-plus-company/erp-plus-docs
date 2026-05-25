# ERP Core

ERP Core is the foundational engine of ERP Plus.

It provides shared platform capabilities used across all domain engines.

---

# Purpose

ERP Core exists to provide:

- platform primitives
- shared abstractions
- authentication foundations
- reusable services

---

# Responsibilities

ERP Core is responsible for:

- authentication
- authorization foundations
- shared service objects
- common concerns
- shared validations
- platform-wide utilities

---

# Public APIs

Examples:

```ruby
ErpCore::AuthenticationService
ErpCore::AuthorizationService
```

Only public services should be consumed by other engines.

---

# Dependencies

ERP Core should have minimal dependencies.

Other engines may depend on ERP Core.

ERP Core should avoid depending on domain engines.

---

# Boundaries

ERP Core MUST NOT:

- contain business-specific logic
- contain inventory logic
- contain billing logic
- contain account-specific workflows

---

# Stability Requirements

ERP Core should evolve slowly.

Changes inside ERP Core may affect the entire platform.

---

# Future Evolution

Possible future responsibilities:

- platform events
- shared observability primitives
- cross-engine abstractions

---

# Ownership

Primary Owner:

Platform Architecture Team
