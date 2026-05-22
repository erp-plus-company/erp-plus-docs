# Modular Monolith

ERP Plus uses a modular monolith architecture.

---

## Why?

Instead of microservices:

- simpler deployment
- shared database
- faster development
- lower operational cost

---

## Structure

Each module is a Rails Engine:

```txt
engines/
  erp_core
  erp_accounts
  erp_users
```

---

## Benefits

- Clear boundaries
- Reusable modules
- Independent testing
- Scalable design
