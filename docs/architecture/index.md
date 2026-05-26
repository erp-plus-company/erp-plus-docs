# Architecture Reading Guide

This section contains the detailed architectural foundations of ERP Plus.

Unlike the System Blueprint, which explains how the platform operates as a whole, this section focuses on specific architectural concepts and design decisions.

---

## Contents

### Modular Monolith

Understand why ERP Plus uses a modular monolith instead of microservices.

Topics covered:

- rationale
- benefits
- trade-offs
- scalability model

→ [Modular Monolith](../architecture/memodular-monolith.md)

---

### Engine Design

Understand the domain structure of ERP Plus.

Topics covered:

- available engines
- responsibilities
- domain boundaries
- engine ownership

→ [Engines Overview](../architecture/engines.md)

---

### Multi-tenancy

Understand how ERP Plus isolates organizations and data.

Topics covered:

- account model
- tenant isolation
- request scoping
- security boundaries

→ [Multi-tenancy](../architecture/multitenancy.md)

---

## Relationship with System Blueprint

If you are new to ERP Plus, read first:

- System Overview
- System Blueprint
- Data Flow

Then continue with this section.

---

## Goal

This section exists to explain:

- architectural decisions
- system structure
- design rationale

without duplicating operational documentation.
