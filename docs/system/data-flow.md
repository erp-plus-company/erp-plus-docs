# 🔄 ERP Plus Data Flow

This document explains how data flows through ERP Plus when a real user interacts with the system.

---

# 🧠 Core Concept

ERP Plus is not a set of isolated engines.

It is a **single system where requests travel through multiple bounded contexts (engines)** in a controlled and predictable way.

---

# 🚀 High-Level Request Flow

Every request in ERP Plus follows this pipeline:

```bash
User Request
  → Authentication (erp_users)
  → Account Resolution (erp_accounts)
  → Authorization Layer
  → Domain Engine (business logic)
  → Background Jobs (erp_workers)
  → Response
```

---

# 🔐 Step 1 — Authentication (erp_users)

When a request enters the system:

- user is authenticated
- session/token is validated
- user identity is resolved

Output:

```bash
CurrentUser context is established
```

---

# 🏢 Step 2 — Account Resolution (erp_accounts)

Next step:

- system determines which account the user belongs to
- loads organization context
- applies account scope globally

Output:

```bash
CurrentAccount is attached to request context
```

---

# 🔒 Step 3 — Authorization Layer

After authentication + account:

- permissions are evaluated
- roles are checked
- access rules are enforced

Important:

> Authorization is centralized, NOT inside engines

---

# ⚙️ Step 4 — Domain Engine Execution

Now the request enters the correct engine:

Example flows:

## 🧑 Users Engine

```bash
Create user
Update profile
Manage roles
```

## 📦 Inventory Engine

```bash
Create product
Update stock
Reserve inventory
```

# 👷 Workers Engine

Used when:

- async processing is required
- heavy operations are offloaded

Example:

- stock recalculation
- email notifications
- data sync jobs

---

# 🔁 Step 5 — Background Processing (erp_workers)

If the engine triggers async work:

- job is pushed to queue
- Solid Queue processes it
- results are stored or emitted

Flow:

```bash
Engine → Job Queue → Worker → Execution → DB update / side effect
```

---

# 📡 Step 6 — Response Assembly

Finally:

- domain result is returned
- serialized
- sent to frontend/API consumer

## 🧩 Cross-Engine Communication Rules

Engines NEVER communicate directly.

Allowed patterns:

### 1. Service Calls

```ruby
ErpAccounts::AccountService.resolve(...)
```

### 2. Domain Events (future evolution)

Planned:

- event-driven communication
- decoupled execution between engines

## ❌ Forbidden Flow

Engines MUST NOT:

- call models from other engines directly
- bypass services
- share internal state
- depend on internal logic of other engines

## 🧠 Real Example Flow

### Scenario: User creates a product

```bash
1. User logged in → erp_core
2. Account loaded → erp_accounts
3. Permission checked
4. Request routed to erp_inventory
5. Product created
6. Worker updates stock cache
7. Response returned
```

## ⚡ Key Insight

ERP Plus is:

> not a collection of engines
> but a controlled data flow system across bounded contexts

## 🧠 Mental Model

Think of ERP Plus as:

```bash
Request → Pipeline → Engines → Jobs → Response
```

NOT:

- separate modules
- independent apps
- microservices

## 🚀 Why this document is critical

This ensures:

- ✔ everyone understands system behavior
- ✔ debugging becomes predictable
- ✔ onboarding becomes easier
- ✔ architecture remains consistent
- ✔ engines don’t become chaotic

## 🧭 Summary

If you understand this flow:

👉 you understand ERP Plus completely
