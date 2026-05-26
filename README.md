# ERP Plus Documentation

Official documentation repository for ERP Plus.

ERP Plus is a modular ERP platform built using a Modular Monolith architecture with Rails Engines, designed to support multi-account business management at scale.

---

## Purpose

This repository is the single source of truth for ERP Plus documentation.

It contains:

- Architecture documentation
- Governance and organizational decisions
- System design
- Engine documentation
- Development workflows
- Operational guides
- Security documentation
- Architecture Decision Records (ADRs)

---

## Documentation Website

The published documentation is available at:

https://erp-plus-company.github.io/erp-plus-docs/

---

## Documentation Structure

```text
docs/
│
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

### Organization

Explains:

- GitHub organization structure
- Repository responsibilities
- Ownership model
- Visibility model

### System

Explains:

- Platform blueprint
- Data flow
- Engine contracts
- Governance model
- Operational model

### Architecture

Explains:

- Modular Monolith design
- Engine architecture
- Multi-tenancy model

### Engines

Engine-specific documentation:

- erp_core
- erp_accounts
- erp_users
- erp_workers
- erp_inventory

### Development

Engineering workflows:

- Git workflow
- Pull Requests
- Testing
- Coding standards

### Operations

Operational concerns:

- CI/CD
- Deployments
- Environments
- Rollback procedures
- Security practices

### Decisions

Architecture Decision Records (ADRs).

---

## Technology Stack

Documentation is built using:

- MkDocs
- Material for MkDocs
- GitHub Pages

---

## Local Development

Install dependencies:

```bash
pip install mkdocs-material
```

Run locally:

```bash
mkdocs serve
```

Open:

```text
http://127.0.0.1:8000
```

---

## Build Documentation

```bash
mkdocs build
```

Generated files:

```text
site/
```

---

## Contributing

Documentation changes should:

- preserve architectural consistency
- follow existing terminology
- avoid duplicating content
- update related sections when necessary

When introducing significant architectural changes:

- update documentation
- update ADRs when applicable

---

## ERP Plus Platform

This repository documents the ERP Plus platform.

The platform itself is composed of:

```text
erp_plus
├── erp_core
├── erp_accounts
├── erp_users
├── erp_workers
└── erp_inventory
```

The documentation repository is responsible for documenting the platform, not implementing it.

---

## License

Copyright © ERP Plus Company.
