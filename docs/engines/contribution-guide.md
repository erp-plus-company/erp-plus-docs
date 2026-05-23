# 🧩 Engine Contribution Guide (ERP Plus)

This document defines the official rules for **creating, modifying, and maintaining Rails Engines** inside ERP Plus.

---

# 🧠 Core Philosophy

Each engine in ERP Plus is:

> a bounded domain module with strict ownership, clear interfaces, and zero hidden coupling.

Engines are NOT folders.

They are **mini-products inside the system**.

---

# 🏗 Engine Types

| Engine        | Responsibility                                                      |
| ------------- | ------------------------------------------------------------------- |
| erp_core      | Shared domain primitives (minimal logic), Authentication & identity |
| erp_accounts  | Tenancy + organizations                                             |
| erp_users     | manage                                                              |
| erp_workers   | Background jobs                                                     |
| erp_inventory | Stock & operations                                                  |

---

# 🚨 Engine Rules (NON-NEGOTIABLE)

Every engine MUST:

- be isolated
- avoid internal dependencies from other engines
- expose only public interfaces
- be independently testable
- respect multi-tenancy boundaries

---

# ❌ Forbidden Patterns

Engines MUST NOT:

- call internal models of another engine
- share business logic directly
- bypass service layers
- depend on ActiveRecord internals across engines
- introduce circular dependencies

---

# 🔌 Allowed Communication Patterns

Engines CAN communicate only via:

## ✔ Public Services

```ruby
ErpUsers::Services::CreateUser.call(...)
```

---

# ✔ Public Interfaces

Defined contracts exposed by each engine.

---

# ✔ Events (Future-ready design)

- domain events
- message-based communication (future evolution)

---

# 🧱 Creating a New Engine

## Step 1 — Generate engine

```bash
rails plugin new engines/erp_new_engine --full --mountable
```

## Step 2 — Register engine

Add to main application:

```ruby
# config/application.rb

config.paths.add "engines/erp_new_engine/lib"
```

## Step 3 — Define namespace

```ruby
module ErpNewEngine
end
```

## Step 4 — Mount engine

```ruby
# config/routes.rb

mount ErpNewEngine::Engine, at: "/erp_new_engine"
```

## Step 5 — Define engine boundaries

Each engine MUST clearly define:

- domain responsibility
- public API
- internal services
- models (if needed)

---

# 🧪 Engine Testing Rules

Every engine MUST include:

- unit tests
- service tests
- optional feature/system tests

```bash
bundle exec rspec engines/erp_users
```

---

# 🧠 Engine Structure Standard

```bash
engines/erp_users/
├── app/
│   ├── controllers/
│   ├── models/
│   ├── services/
│   └── views/
├── lib/
├── config/
├── spec/
└── erp_users.gemspec
```

---

# 🔒 Engine Isolation Rules

Engines MUST:

## ✔ Allowed

- call public services from other engines
- use shared interfaces
- use core engine primitives

## ❌ Not allowed

- direct model access across engines
- internal service calls between engines
- shared database logic without interface

---

# 🧠 Dependency Direction Rule

Engine dependencies MUST flow like this:

```bash
erp_core → all engines
erp_accounts → users/workers/inventory
erp_users → workers
erp_inventory → workers
```

Never reverse dependencies.

---

# 🧩 Core Engine Responsibility

**erp_core**

- shared domain logic
- base services
- global helpers

BUT:

> MUST remain minimal and stable

---

# 👥 Ownership Model

Each engine has:

- clear owner responsibility
- isolated domain logic
- independent test suite

---

# 🚀 Contribution Workflow

To modify an engine:

## 1. Create feature branch

```bash
feature/<engine>/<change>
```

Example:

```bash
feature/erp_users/invitation-flow
```

## 2. Make changes inside engine ONLY

Do NOT modify other engines.

## 3. Add tests inside engine spec

## 4. Open PR with engine scope clearly defined

---

# 🔍 Engine Review Checklist

Before approval:

- [ ] Engine boundaries respected
- [ ] No cross-engine internal coupling
- [ ] Public services used correctly
- [ ] Tests included
- [ ] Multi-tenancy respected
- [ ] No shared hidden logic introduced

---

📦 Versioning Engines (IMPORTANT)

Each engine SHOULD evolve independently.

Future-ready model:

erp_users v1.0
erp_inventory v1.0
erp_workers v1.0
🧠 Mental Model
Engine = Mini Product inside ERP Plus
⚡ Why this exists

Without this guide:

engines become coupled
architecture degrades
system becomes monolith spaghetti

With this guide:

✔ scalable architecture
✔ clear ownership
✔ enterprise-grade modularity
✔ safe external contributions

🧠 Final Definition

An engine is a fully isolated domain module that behaves like a mini-application inside a controlled monolith ecosystem.
