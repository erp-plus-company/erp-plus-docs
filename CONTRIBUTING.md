# Contributing to ERP Plus Documentation

Thank you for helping improve ERP Plus documentation.

This repository is the official documentation source for the ERP Plus platform.

---

# Purpose

The goal of this repository is to document:

- Organization governance
- System architecture
- Engine design
- Development workflows
- Operations
- Security practices
- Architectural decisions (ADRs)

This repository does not contain application code.

---

# Documentation Principles

Documentation should be:

- Clear
- Concise
- Accurate
- Maintainable
- Architecture-driven

Documentation should explain:

- why something exists
- what it does
- how it behaves

before explaining implementation details.

---

# Repository Structure

```txt
docs/
├── organization/
├── system/
├── architecture/
├── engines/
├── getting-started/
├── development/
├── deployment/
├── security/
└── decisions/
```

Each section has a specific responsibility.

Avoid duplicating information across sections.

---

# Documentation Ownership

The documentation repository is the source of truth for:

- platform knowledge
- architecture decisions
- engineering standards
- operational guidance

Documentation should be updated whenever architecture or workflows change.

---

# Before Submitting Changes

Verify that:

- content belongs in the correct section
- no duplicate documentation is introduced
- links remain valid
- markdown formatting is consistent

---

# Pull Requests

Documentation Pull Requests should:

- have a clear purpose
- remain focused in scope
- avoid unrelated changes
- explain why the change is needed

---

# Writing Style

Use:

- short paragraphs
- descriptive headings
- architecture-first explanations
- consistent terminology

Prefer:

```txt
Engine
Multi-tenancy
Host Application
Bounded Context
Modular Monolith
```

Avoid inventing alternative terms for the same concept.

---

# Architecture Changes

If documentation reflects a new architectural decision:

1. Update the relevant documentation.
2. Create or update an ADR if necessary.
3. Ensure all related sections remain consistent.

---

# Questions

If documentation structure is unclear:

- Organization → governance and repositories
- System → platform behavior
- Architecture → architectural concepts
- Engines → engine-specific information
- Development → contributor workflows
- Operations → deployment and runtime concerns

---

# Thank You

Good documentation is part of the product.

Thank you for helping keep ERP Plus understandable, maintainable, and scalable.
