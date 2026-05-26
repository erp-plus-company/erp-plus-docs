# ERP Plus System Blueprint

This document is the **master blueprint of ERP Plus**, combining architecture, engines, data flow, and system design into a single mental model.

---

## What is ERP Plus?

ERP Plus is a:

> Modular multi-account ERP platform built as a Rails modular monolith using Engines.

---

## System Identity

ERP Plus is NOT:

- ❌ a monolith legacy app
- ❌ a microservices system
- ❌ a collection of independent engines

ERP Plus IS:

> a single coordinated system composed of isolated domain engines with strict contracts and controlled data flow.

---

## Global Architecture Map

```bash
ERP Plus System
│
├── 🌐 Entry Layer (Requests)
│   └── API / Web / Frontend
│
├── 🔐 Identity Layer
│   ├── erp_core (authentication)
│   └── erp_accounts (accounts)
│
├── ⚙️ Domain Layer (Engines)
│   ├── erp_users
│   ├── erp_inventory
│   ├── erp_workers
│   └── others
│
├── 🔁 Execution Layer
│   └── erp_workers (background jobs)
│
└── 📡 Infrastructure Layer
    ├── PostgreSQL
    ├── Solid Stack
    ├── Docker
    ├── Kamal
    └── GitHub Actions CI/CD
```

---

## System Flow (Unified Model)

Every action in ERP Plus follows this pattern:

```bash
Request
  → Authentication (erp_core)
  → Account Resolution (erp_accounts)
  → Authorization Layer
  → Domain Engine Execution
  → Optional Background Jobs (erp_workers)
  → Response
```

---

## Engine System Model

Each engine behaves as:

> a bounded context inside a controlled monolith

### Engine Responsibilities

Each engine MUST:

- own its domain logic
- expose public services
- avoid internal leakage
- respect account boundaries

### Engine Isolation Model

```bash
erp_inventory ❌ cannot access erp_users internals
erp_workers ❌ cannot modify domain logic
erp_core ✔ shared utilities only
```

---

## Communication Model

Engines communicate ONLY via:

### 1. Public Services

```ruby
ErpInventory::ProductService.create(...)
```

### 2. Domain Interfaces

Defined explicitly per engine.

### 3. Future: Domain Events

Planned evolution toward:

- event-driven architecture
- async cross-engine communication

---

## Multi-Account Model

ERP Plus is account-first:

Every request is scoped by:

- organization
- account
- account context

```bash
User → Account → Data Scope → Engine Logic
```

---

## Execution Model

Domain logic is executed inside engines:

- synchronous for simple operations
- asynchronous via workers for heavy tasks

---

## Background System

erp_workers handles:

- async jobs
- retries
- scheduled tasks
- heavy computations

Flow:

```bash
Engine → Job → Queue → Worker → Side Effect → Persistence
```

---

## Security Model

Security is enforced at multiple layers:

- authentication (erp_core)
- account isolation (erp_accounts)
- authorization layer
- engine-level rules
- CI security scanning

---

## Infrastructure Model

ERP Plus runs on:

- Docker (local + production)
- Kamal (deployment)
- GitHub Actions (CI/CD)
- PostgreSQL (data)
- Solid Stack (jobs, cache, real-time)

---

## System Design Principles

ERP Plus follows:

### 1. Isolation

Engines are independent bounded contexts.

### 2. Explicit Communication

No hidden coupling between engines.

### 3. Account-first Design

Everything is multi-account by default.

### 4. Infrastructure Awareness

System is designed for real production deployment.

### 5. Security by Default

Security is built into every layer.

---

## Mental Model (MOST IMPORTANT)

Think of ERP Plus as:

```bash
A single system composed of isolated domain engines connected through controlled flows and strict contracts.
```

---

## Scaling Model

ERP Plus scales by:

- adding new engines
- not modifying existing ones
- extending via services
- keeping strict boundaries

---

## Final System View

```bash
User → Identity → Account → Domain Engine → Worker → Response
```

---

## Why this blueprint exists

This file is the:

- 🧠 architectural truth
- 📐 system map
- 🔌 engine coordination model
- 🚀 scaling guide
- 📚 onboarding reference

---

## Final Statement

ERP Plus is:

> a controlled modular ecosystem where every engine behaves like a mini-product inside a single governed platform.
