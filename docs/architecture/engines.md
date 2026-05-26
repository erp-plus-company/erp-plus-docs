# Engines Overview

ERP Plus is composed of domain-oriented Rails Engines.

Each engine owns a specific business capability and acts as a bounded context inside the platform.

---

## Engine Map

| Engine        | Responsibility                       |
| ------------- | ------------------------------------ |
| erp_core      | Shared platform services             |
| erp_accounts  | Organizations and account management |
| erp_users     | Authentication and user management   |
| erp_workers   | Background jobs and async processing |
| erp_inventory | Inventory and stock management       |

---

## Platform Structure

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

## Architectural Principles

All engines must:

- own their domain logic
- expose explicit interfaces
- remain independently testable
- respect multi-tenancy boundaries

---

## Why Engines Exist

Engines allow ERP Plus to:

- separate business domains
- scale engineering teams
- isolate responsibilities
- reduce coupling
- evolve independently

---

## Related Documentation

Detailed engine documentation:

→ [erp_core](../engines/erp_core/index.md)

→ [erp_accounts](../engines/erp_accounts/index.md)

→ [erp_users](../engines/erp_users/index.md)

→ [erp_workers](../engines/erp_workers/index.md)

→ [erp_inventory](../engines/erp_inventory/index.md)

Engine behavior and rules:

→ [Rules Engine](../system/engine-contracts.md)
