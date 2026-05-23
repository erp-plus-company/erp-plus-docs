# 👥 ERP Plus Roles & Access Model

This document defines how different roles interact with the ERP Plus system and documentation.

It is designed for **startup → enterprise scale onboarding clarity**.

---

# 🧠 Core Principle

ERP Plus documentation is NOT flat.

It is:

> role-aware, permission-aware, and context-aware

Different users should NOT consume the same depth of system information.

---

# 🧭 Role-Based Documentation Model

ERP Plus defines 4 primary roles:

```txt id="roles"
- Backend Developer
- Frontend Developer
- DevOps Engineer
- QA Engineer
```

Each role has a different lens into the system.

---

# 🔵 Backend Developer View

## Access Level: FULL DOMAIN LAYER

### Backend developers can access:

- architecture/
- engines/
- system/
- development/
- decisions (ADRs)

### Responsibilities:

- implement engine logic
- define domain rules
- maintain services
- ensure engine isolation

### Forbidden:

- modifying infrastructure without review
- bypassing engine contracts

---

# 🟣 Frontend Developer View

## Access Level: API CONSUMER ONLY

### Frontend developers can access:

- system/
- architecture/
- getting-started/
- API contracts (future section)

### Responsibilities:

- consume backend APIs
- build UI/UX
- avoid domain logic

### Forbidden:

- touching engine logic
- modifying backend services
- altering business rules

---

# 🔴 DevOps Engineer View

## Access Level: INFRASTRUCTURE + DEPLOYMENT

### DevOps engineers can access:

- deployment/
- security/
- system/
- CI/CD documentation
- architecture (infrastructure sections)

### Responsibilities:

- CI/CD pipelines
- deployments (Kamal)
- monitoring
- security enforcement

### Forbidden:

- modifying domain logic
- altering business rules
- touching engine internals

---

# 🟡 QA Engineer View

## Access Level: SYSTEM BEHAVIOR ONLY

### QA engineers can access:

- system/
- architecture/
- engines (behavior only)
- testing docs
- decisions (ADRs)

### Responsibilities:

- validate system behavior
- ensure regression safety
- test engines independently

### Forbidden:

- modifying production logic
- implementing features
- changing architecture

---

# 🧠 Documentation Visibility Rules

Not all documentation is equal.

---

# 🔓 Public Layer (All Roles)

- system/index.md
- system/blueprint.md
- getting-started/
- architecture/index.md

---

# 🔐 Technical Layer (Engineers Only)

- engines/
- architecture/modular-monolith.md
- architecture/engines.md

---

# 🔒 Operational Layer (DevOps Only)

- deployment/
- security/
- CI/CD workflows

---

# 🧠 Decision Layer (All Engineers)

- decisions/ (ADRs)

---

# 🚀 Onboarding Flow (REAL WORLD)

When a new developer joins:

## Step 1 — System Understanding

Read:

```bash
system/index.md
system/blueprint.md
```

## Step 2 — Architecture Understanding

Read:

```bash
architecture/
system/data-flow.md
engine-contracts.md
```

## Step 3 — Role-Specific Deep Dive

Depending on role:

- backend → engines/
- frontend → API + system flow
- devops → deployment/
- QA → testing + behavior

## Step 4 — First Contribution

Must follow:

```bash
CONTRIBUTING.md
CI pipeline rules
engine contract rules
```

---

# 🧠 Key Insight

ERP Plus is NOT documented like a project.

It is documented like:

> 🧠 a system with controlled knowledge exposure

---

# ⚠️ WHY THIS MATTERS (CRITICAL)

Without this model:

- frontend devs break backend rules
- QA misunderstands engine boundaries
- DevOps touches domain logic
- external devs get lost
- architecture becomes inconsistent

---

# 🚀 SCALING IMPACT

This structure enables:

- ✔ onboarding external teams safely
- ✔ parallel development across roles
- ✔ reduced architectural mistakes
- ✔ clear responsibility boundaries
- ✔ enterprise-grade maintainability

---

# 🧠 FINAL MENTAL MODEL

```bash
Same system → different perspectives → controlled knowledge exposure
```
