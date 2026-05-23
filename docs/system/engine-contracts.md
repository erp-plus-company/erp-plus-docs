# 🔌 Engine Contracts — ERP Plus

This document defines the **official architectural contract** for all Rails Engines inside ERP Plus.

---

# 🧠 What is an Engine?

An ERP Plus engine is a **self-contained domain module** inside the modular monolith.

Each engine represents a business capability, such as:

- Authentication
- Accounts / Tenancy
- Users
- Workers
- Inventory

---

# ⚠️ Core Principle

> Engines are independent, but not isolated from the system.

They must interact through **explicit contracts**, not implicit coupling.

---

# 🧩 Engine Structure Standard

Every engine MUST follow this structure:

```txt id="structure"
engines/erp_example/
├── app/
├── config/
├── lib/
├── public_api.rb
├── domain/
├── services/
└── README.md
```

---

# 🔒 Engine Responsibilities

Each engine MUST:

- Own its domain logic completely
- Expose a public interface (API/service layer)
- Avoid leaking internal models
- Be independently testable

---

# ❌ Forbidden Rules (CRITICAL)

Engines MUST NOT:

- ❌ Access internal models of other engines
- ❌ Use Engines::OtherEngine::Model directly
- ❌ Share business logic across engines
- ❌ Bypass public APIs/services
- ❌ Depend on implementation details of other engines

---

# 🔌 Communication Between Engines

All communication MUST happen through:

## 1. Public Services

Example:

```bash
ErpUsers::UserService.create_user(...)
```

## 2. Domain APIs

Each engine may expose:

- service objects
- query objects
- facades

## 3. Events (Future Design)

Planned architecture evolution:

- domain events
- async communication between engines

---

# 📦 Public API Requirement

Each engine MUST expose a public interface file:

```bash
public_api.rb
```

This file defines:

- allowed entry points
- service exposure
- external contract

---

# 🧠 Dependency Rules

Engine dependencies MUST follow these rules:

## Allowed

- `erp_core` can be used by all engines
- `erp_accounts` can be referenced by domain services
- shared utilities only via `erp_core`

## Forbidden

- circular dependencies between engines
- direct model coupling
- cross-engine migrations logic

---

# 🧪 Testing Contract

Each engine MUST be tested in isolation:

- unit tests inside engine
- integration tests via system layer
- no reliance on other engine internals

---

# 📦 Versioning Strategy (IMPORTANT)

Each engine SHOULD be versioned logically:

```bash
erp_users v1.0.0
erp_accounts v1.0.0
```

Rules:

- breaking changes → version bump
- internal refactors → no version bump
- public API changes → documented explicitly

---

# 🔐 Security Boundary

Each engine is responsible for:

- enforcing authorization rules
- respecting account boundaries
- avoiding data leakage across domains

Security is enforced at:

- service layer
- not model layer

---

# 🚀 Scaling Model

ERP Plus scales by:

- adding new engines
- not modifying existing ones
- extending via services instead of coupling

---

# 🧠 Mental Model

Think of each engine as:

> a micro-product inside a controlled ecosystem

---

# ⚡ Why this document matters

This is the document that ensures:

- architecture does NOT collapse over time
- multiple teams can work in parallel
- engines remain independent
- system stays maintainable at scale

---

# 🧭 Summary

If you follow this contract:

- ✔ engines stay clean
- ✔ system scales horizontally
- ✔ onboarding becomes predictable
- ✔ coupling is controlled
- ✔ architecture remains stable
