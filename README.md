# ERP Plus Documentation

Official documentation repository for ERP Plus.

This repository is the authoritative source of truth for platform architecture, engineering workflows, governance, operational procedures, and architectural decisions.

---

## Purpose

ERP Plus Documentation exists to document:

- platform architecture
- system behavior
- engineering standards
- development workflows
- operational practices
- security policies
- architecture decision records (ADRs)

This repository documents the platform.

It does not contain application code.

---

# ERP Plus Platform

ERP Plus is a modular ERP platform built with Rails 8.

The platform follows a Modular Monolith architecture based on Rails Engines.

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

# Documentation Philosophy

Documentation is treated as a first-class engineering artifact.

ERP Plus follows a:

```txt
Documentation First
```

approach.

Architecture, workflows, and decisions must be documented before becoming organizational standards.

---

## Documentation Website

Published documentation:

```txt
https://erp-plus-company.github.io/erp-plus-docs/
```

---

# Documentation Scope

This repository contains:

- Architecture documentation
- Development workflows
- Platform governance
- Security documentation
- Operational procedures
- ADRs
- Engine documentation

---

# Engineering Workflow

ERP Plus development is managed through:

- Taiga
- GitHub
- GitHub Actions

The official workflow is:

```txt
Epic (optional)
 ↓
User Story
 ↓
Task
 ↓
Branch
 ↓
Pull Request
 ↓
Review
 ↓
Merge
 ↓
Release
```

---

# Taiga Integration

ERP Plus uses Taiga as the primary project management platform.

Work is organized through:

- Epics
- User Stories
- Tasks
- Issues
- Sprints

Current sprint duration:

```txt
2 weeks
```

---

# Contributor Models

ERP Plus supports two contributor models.

## Internal Contributors

Internal contributors work through:

```txt
Taiga
 ↓
User Story
 ↓
Branch
 ↓
Pull Request
```

Branch example:

```bash
feature/TG-123-user-invitations
```

---

## Community Contributors

Community contributors do not require Taiga access.

Branch example:

```bash
feature/user-invitations
```

Community contributions are submitted through Pull Requests.

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
├── operations/
└── decisions/
```

### Organization

Defines:

- repository ownership
- governance model
- visibility rules
- organizational structure

### System

Defines:

- platform behavior
- engine contracts
- data flow
- operational model

### Architecture

Defines:

- modular monolith architecture
- engine boundaries
- multi-tenancy

### Engines

Engine-specific documentation.

Examples:

```txt
erp_core
erp_accounts
erp_users
erp_workers
erp_inventory
```

### Development

Defines:

- workflows
- feature lifecycle
- pull request standards
- coding standards
- testing requirements

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

# Documentation Governance

Documentation must be updated whenever:

- architecture changes
- workflows change
- engineering standards change
- deployment processes change

Documentation is considered part of the Definition of Done.

---

## Contributing

Before contributing:

Read:

```txt
CONTRIBUTING.md
```

Documentation changes should:

- avoid duplication
- preserve terminology
- remain architecture-driven
- stay consistent with ADRs

---

## License

Copyright © ERP Plus Company.
