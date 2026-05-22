# Engines Architecture

ERP Plus is composed of isolated Rails Engines.

---

## Engines

| Engine        | Responsibility                |
| ------------- | ----------------------------- |
| erp_core      | Base system logic             |
| erp_accounts  | Multi-tenancy + organizations |
| erp_users     | Authentication & users        |
| erp_workers   | Background jobs               |
| erp_inventory | Stock management              |

---

## Rules

- No engine should depend on internal implementation of another
- Communication must be explicit
- Shared logic goes in erp_core
