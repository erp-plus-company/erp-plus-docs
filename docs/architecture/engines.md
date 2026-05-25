# Engines Overview

ERP Plus is composed of domain-oriented Rails Engines.

Each engine owns a specific business capability.

---

# Engine Map

| Engine        | Responsibility                       |
| ------------- | ------------------------------------ |
| erp_core      | Shared platform services             |
| erp_accounts  | Organizations and account management |
| erp_users     | Authentication and user management   |
| erp_workers   | Background jobs and async processing |
| erp_inventory | Inventory and stock management       |

---

# Platform Structure

```txt
ERP Plus
│
├── erp_core
├── erp_accounts
├── erp_users
├── erp_workers
└── erp_inventory
```

---

# Engine Responsibilities

## erp_core

Provides:

- authentication
- shared services
- platform abstractions
- common utilities

---

## erp_accounts

Responsible for:

- organizations
- account context
- account isolation

---

## erp_users

Responsible for:

- user lifecycle
- identity management

---

## erp_workers

Responsible for:

- asynchronous jobs
- retries
- scheduled processing

---

## erp_inventory

Responsible for:

- products
- stock management
- inventory operations

---

# Why Engines Exist

Engines allow ERP Plus to:

- separate business domains
- scale development teams
- isolate responsibilities
- reduce coupling

---

# Related Documentation

For engine rules and contracts see:

→ System Blueprint / Engine Contracts
