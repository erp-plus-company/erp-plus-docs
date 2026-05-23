# 🧠 ERP Plus System Overview

ERP Plus is a modular multi-account ERP platform built as a **modular monolith using Rails Engines**.

Its design follows strict boundaries, clear ownership per module, and a scalable architecture intended to support long-term enterprise growth.

---

# 🧭 System Philosophy

ERP Plus is built on 5 core principles:

## 1. Modular Monolith Architecture

The system is a single Rails application composed of isolated engines.

Each engine is:

- self-contained
- domain-focused
- independently maintainable

---

## 2. Engine Isolation

Engines must NOT:

- directly depend on internal implementation of other engines
- share business logic implicitly
- bypass defined interfaces

Communication MUST happen through:

- public services
- APIs
- domain contracts

---

## 3. Multi-Tenancy First

The system is designed to support multiple account from day one.

Tenancy rules apply across:

- authentication
- data access
- business logic
- background jobs

---

## 4. Infrastructure-Aware Design

ERP Plus is designed to run in production using:

- Docker
- Kamal deployments
- GitHub Actions CI/CD
- PostgreSQL
- Redis-backed services (Solid Stack)

---

## 5. Security by Default

Security is not optional:

- secrets never live in repo
- CI includes Brakeman scanning
- dependency updates are automated
- deployment is protected
- engines must respect data boundaries

---

# 🏗 System Architecture

```bash
ERP Plus
│
├── Core Rails Application
│
├── Engines (Domain Modules)
│   ├── erp_core
│   ├── erp_accounts
│   ├── erp_users
│   ├── erp_workers
│   └── erp_inventory
│
├── Infrastructure Layer
│   ├── Docker
│   ├── Kamal Deploy
│   ├── GitHub Actions CI/CD
│
└── Shared Concerns
    ├── Authentication (Devise)
    ├── Authorization
    ├── Multi-tenancy
    └── Background Jobs
```

---

# 🔌 Engine Communication Model

Engines interact using strict rules:

## Allowed:

- calling public services
- using shared interfaces
- event-based communication (future)

## Forbidden:

- direct model access across engines
- cross-engine business logic leakage
- tight coupling via internal classes

---

# 👥 System Roles (Mental Model)

ERP Plus assumes these system actors:

## Backend Developer

- builds engines
- defines domain logic
- owns APIs

## Frontend Developer

- consumes engine outputs
- builds UI via APIs
- does NOT touch domain rules

## DevOps Engineer

- owns CI/CD pipelines
- manages deployments
- monitors infrastructure

## QA Engineer

- validates behavior
- ensures regression safety
- tests engines independently

---

# 🚀 Deployment Model

ERP Plus uses:

- GitHub Actions CI/CD
- Docker containers
- Kamal deployment system

Flow:

`Code → PR → CI (test + security) → Merge → Deploy via Kamal`

---

📊 Scaling Strategy

ERP Plus scales by:

- adding new engines (not modifying core)
- keeping bounded contexts isolated
- enforcing strict CI rules
- avoiding cross-domain coupling

---

# 🔐 Security Model

- secrets managed outside repo
- Brakeman static analysis in CI
- dependency updates via Dependabot
- protected branches (main/develop)
- audit-friendly deployment workflow

---

# 📚 Documentation Structure

This documentation is structured to serve:

- new developers
- external contributors
- DevOps engineers
- system maintainers

Each section of docs is designed for a different **audience lens**, not a different repo.

---

# 🧠 Final Mental Model

ERP Plus is:

> A modular Rails platform where each engine behaves like a mini-product inside a controlled ecosystem.

---

# ⚡ Why this file is critical

This file becomes:

- ✔ onboarding entry point
- ✔ architecture truth source
- ✔ system design reference
- ✔ scaling guide
- ✔ decision baseline
