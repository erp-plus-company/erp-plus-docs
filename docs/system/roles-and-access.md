# ERP Plus Roles & Access Model

This document defines how different roles interact with the ERP Plus system and documentation.

It is designed for **startup → enterprise scale onboarding clarity**.

---

## Core Principle

ERP Plus documentation is NOT flat.

It is:

> role-aware, permission-aware, and context-aware

Different users should NOT consume the same depth of system information.

---

## Role-Based Documentation Model

ERP Plus defines 4 primary roles:

```bash
- Backend Developer
- Frontend Developer
- DevOps Engineer
- QA Engineer
```

Each role has a different lens into the system.

---

## Backend Developer View

### Access Level: FULL DOMAIN LAYER

#### Backend developers can access:

→ [Architecture](../architecture/index.md)

→ [Engines](../engines/contribution-guide.md)

→ [System](../system/index.md)

→ [Development](../development/workflow.md)

→ [Decisions (ADRs)](../decisions/adr-0001-modular-monolith.md)

#### Responsibilities:

- implement engine logic
- define domain rules
- maintain services
- ensure engine isolation

#### Forbidden:

- modifying infrastructure without review
- bypassing engine contracts

---

## Frontend Developer View

### Access Level: API CONSUMER ONLY

#### Frontend developers can access:

→ [System](../system/index.md)

→ [Architecture](../architecture/index.md)

→ [Getting Started](../getting-started/index.md)

- API contracts (future section)

#### Responsibilities:

- consume backend APIs
- build UI/UX
- avoid domain logic

#### Forbidden:

- touching engine logic
- modifying backend services
- altering business rules

---

## DevOps Engineer View

### Access Level: INFRASTRUCTURE + DEPLOYMENT

#### DevOps engineers can access:

→ [Environments](../deployment/environments.md)

→ [Security](../security/policies.md)

→ [System](../system/index.md)

→ [CI/CD documentation](../deployment/ci-cd.md)

→ [architecture (infrastructure sections)](../architecture/index.md)

#### Responsibilities:

- CI/CD pipelines
- deployments (Kamal)
- monitoring
- security enforcement

#### Forbidden:

- modifying domain logic
- altering business rules
- touching engine internals

---

## QA Engineer View

### Access Level: SYSTEM BEHAVIOR ONLY

#### QA engineers can access:

→ [System](../system/index.md)

→ [Architecture](../architecture/index.md)

→ [Engines](../engines/contribution-guide.md)

→ [Testing docs](../development/testing.md)

→ [Decisions (ADRs)](../decisions/adr-0001-modular-monolith.md)

#### Responsibilities:

- validate system behavior
- ensure regression safety
- test engines independently

#### Forbidden:

- modifying production logic
- implementing features
- changing architecture

---

## Documentation Visibility Rules

Not all documentation is equal.

---

## Public Layer (All Roles)

→ [System](../system/index.md)

→ [Blueprint](../system/blueprint.md)

→ [Getting Started](../getting-started/index.md)

→ [Architecture](../architecture/index.md)

---

## Technical Layer (Engineers Only)

→ [Engines](../engines/contribution-guide.md)

→ [Modular Monolith](../architecture/modular-monolith.md)

→ [Engines Overview](../architecture/engines.md)

---

## Operational Layer (DevOps Only)

→ [Environments](../deployment/environments.md)

→ [Security Policies](../security/policies.md)

→ [CI/CD](../deployment/ci-cd.md)

---

## Decision Layer (All Engineers)

→ [Decisions](../decisions/adr-0001-modular-monolith.md)

---

## Onboarding Flow (REAL WORLD)

When a new developer joins:

### Step 1 — System Understanding

Read:

→ [Overview](../system/index.md)

→ [Blueprint](../system/blueprint.md)

### Step 2 — Architecture Understanding

Read:

→ [Reading Guide](../architecture/index.md)

→ [Data Flow](../system/data-flow.md)

→ [Engine Contracts](../system/engine-contracts.md)

### Step 3 — Role-Specific Deep Dive

Depending on role:

- backend → [Contribution Guide](../engines/contribution-guide.md)

- frontend → [Overview](../system/index.md)

- devops → [CI/CD](../deployment/ci-cd.md)

- QA → [Testing](../development/testing.md)

### Step 4 — First Contribution

Must follow:

```bash
CONTRIBUTING.md
```

→ [CI/CD](../deployment/ci-cd.md)

→ [Contribution Guide](../engines/contribution-guide.md)

---

## Key Insight

ERP Plus is NOT documented like a project.

It is documented like:

> 🧠 a system with controlled knowledge exposure

---

## WHY THIS MATTERS (CRITICAL)

Without this model:

- frontend devs break backend rules
- QA misunderstands engine boundaries
- DevOps touches domain logic
- external devs get lost
- architecture becomes inconsistent

---

## SCALING IMPACT

This structure enables:

- ✔ onboarding external teams safely
- ✔ parallel development across roles
- ✔ reduced architectural mistakes
- ✔ clear responsibility boundaries
- ✔ enterprise-grade maintainability

---

## FINAL MENTAL MODEL

```bash
Same system → different perspectives → controlled knowledge exposure
```
