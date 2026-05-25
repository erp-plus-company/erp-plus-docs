# ERP Accounts

ERP Accounts provides the multi-tenancy foundation of ERP Plus.

---

# Purpose

ERP Accounts ensures that all platform data is scoped correctly to an organization.

---

# Responsibilities

ERP Accounts manages:

- organizations
- accounts
- tenancy boundaries
- account context resolution

---

# Domain Concepts

## Organization

Represents a business entity using ERP Plus.

## Account Context

Defines the current tenant scope for a request.

---

# Public APIs

Examples:

```ruby
ErpAccounts::AccountResolver
ErpAccounts::OrganizationService
```

---

# Dependencies

May depend on:

- erp_core

Should not depend on:

- erp_inventory
- erp_workers

---

# Boundaries

ERP Accounts MUST NOT:

- manage inventory
- manage background jobs
- contain product logic

---

# Security Responsibilities

ERP Accounts is responsible for:

- tenant isolation
- account scoping
- preventing cross-account data access

---

# Future Evolution

Potential future modules:

- subscriptions
- billing context
- organization settings

---

# Ownership

Primary Owner:

Backend Platform Team
