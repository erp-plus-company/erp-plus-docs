# 🔄 Feature Lifecycle (ERP Plus)

This document defines the **end-to-end lifecycle of a feature** inside ERP Plus.

It ensures that every change follows a predictable, scalable engineering flow.

---

# 🧠 Core Principle

A feature is not just code.

It is:

> a lifecycle that moves through engine boundaries, validation layers, and controlled deployment.

---

# 🚀 Feature Lifecycle Flow

```txt id="flow"
Idea → Engine Selection → Branch → Implementation → Tests → PR → CI → Review → Merge → Deploy
```

---

# 1. 💡 Idea Phase

Every feature starts with:

- a problem
- a requirement
- or an improvement

It MUST be assigned to:

- a specific engine

---

# 2. 🧭 Engine Selection

Each feature MUST belong to one primary engine:

| Feature Type       | Engine        |
| ------------------ | ------------- |
| Auth / Users       | erp_users     |
| Accounts / Tenants | erp_accounts  |
| Core logic         | erp_core      |
| Background jobs    | erp_workers   |
| Inventory          | erp_inventory |

---

# 3. 🌿 Branch Creation

All work MUST start from develop:

```bash
git checkout develop
git pull origin develop
git checkout -b feature/my-feature
```

---

# 4. 🛠 Implementation Phase

Rules:

- respect engine boundaries
- no cross-engine internal coupling
- use services instead of direct access
- follow Rails conventions

---

# 5. 🧪 Testing Phase

Every feature MUST include:

- unit tests (domain logic)
- feature tests (user flow)
- engine-specific tests

```bash
bundle exec rspec
```

---

# 6. 🔁 Pull Request Phase

PR MUST:

- follow PR Standard
- declare engine scope
- include tests
- pass CI checks

---

# 7. ⚙️ CI Phase

CI validates:

- Rubocop
- RSpec
- Brakeman
- build integrity

If CI fails:

> feature is not valid

---

# 8. 👀 Review Phase

Review checks:

- architecture compliance
- engine isolation
- multi-tenancy safety
- code quality

---

# 9. 🔀 Merge Phase

Once approved:

- merged into develop
- later released via main

---

# 10. 🚀 Deploy Phase

Deployment flow:

```bash
Merge → CI → Docker Build → Kamal Deploy → Production
```

---

# 🧠 Rules Summary

- every feature belongs to one engine
- no feature bypasses CI
- no feature ignores multi-tenancy
- no feature bypasses PR flow

---

# 📊 Feature Lifecycle Mental Model

```bash
Idea → Engine → Branch → Code → Tests → PR → CI → Review → Merge → Deploy
```

---

# ⚡ Why this matters

Without this lifecycle:

- features become inconsistent
- engines become coupled
- CI loses meaning
- system becomes unpredictable

With this lifecycle:

- ✔ predictable development
- ✔ scalable architecture
- ✔ safe contributions
- ✔ enterprise-ready workflow

---

# 🧠 Final Definition

> A feature in ERP Plus is a controlled lifecycle unit inside a bounded engine, validated by CI and governed by architecture rules.
