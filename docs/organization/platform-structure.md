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

# Platform Components

## Documentation Repository

erp-plus-docs contains:

- architecture documentation
- governance documentation
- development standards
- operational documentation

---

## Host Application

erp_plus contains:

- Rails application
- engine integration
- global configuration
- routing

---

## Domain Engines

Business functionality lives inside engines.

Examples:

- erp_accounts
- erp_users
- erp_workers
- erp_inventory

Engines are not folders.

They are platform domains.

---

# Architectural Principle

Business logic belongs to engines.

The host application should remain thin.

---

# Long-Term Vision

The platform should grow by:

- adding new engines
- preserving boundaries
- avoiding tight coupling

without requiring architectural rewrites.
