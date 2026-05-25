# 🏗 Platform Structure

This document describes how the ERP Plus repositories relate to each other.

---

# High-Level Structure

```txt
erp-plus-company
│
├── erp-plus-docs
│
├── erp_plus
│   │
│   ├── erp_core
│   ├── erp_accounts
│   ├── erp_users
│   ├── erp_workers
│   └── erp_inventory
│
└── future repositories
```

---

# Repository Relationships

## Documentation Repository

erp-plus-docs documents:

- platform architecture
- governance
- workflows
- engines
- deployments

---

## Host Application

erp_plus is responsible for:

- booting Rails
- loading engines
- configuring infrastructure
- deployment orchestration

---

## Engines

Each engine represents a business domain.

Examples:

- Accounts
- Users
- Inventory
- Workers

Engines are not folders.

They are platform domains.

---

# Architectural Rule

All business functionality should live inside engines.

The host application should remain thin.

---

# Long-Term Vision

The platform should be able to grow by:

- adding new engines
- preserving domain boundaries
- avoiding cross-domain coupling

without requiring architectural rewrites.
