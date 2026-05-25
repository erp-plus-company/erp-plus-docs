# ERP Users

ERP Users manages user lifecycle and identity inside ERP Plus.

---

# Purpose

ERP Users provides all user-related functionality.

---

# Responsibilities

ERP Users manages:

- user profiles
- invitations
- memberships
- user lifecycle

---

# Domain Concepts

## User

Represents a person using ERP Plus.

## Membership

Represents a user's relationship to an organization.

## Invitation

Represents onboarding access to the platform.

---

# Public APIs

Examples:

```ruby
ErpUsers::CreateUser
ErpUsers::InviteUser
ErpUsers::MembershipService
```

---

# Dependencies

May depend on:

- erp_core
- erp_accounts

Should not depend on:

- erp_inventory

---

# Boundaries

ERP Users MUST NOT:

- manage inventory
- manage products
- manage background processing

---

# Security Responsibilities

ERP Users is responsible for:

- identity management
- membership validation
- access lifecycle

---

# Future Evolution

Potential future modules:

- MFA
- social login
- audit history
- user preferences

---

# Ownership

Primary Owner:

Backend Identity Team
