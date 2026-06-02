# Repositories

This document describes the repositories that compose ERP Plus.

---

## Core Repositories

### erp_plus

Role:

Host Application.

Responsibilities:

- Rails boot process
- Routing
- Global configuration
- Engine integration

---

### erp-plus-docs

Role:

Official documentation repository.

Responsibilities:

- Architecture
- ADRs
- Governance
- Development guides
- Security documentation
- Operational documentation

---

## Engine Repositories

Current domain repositories:

### erp_core

Shared platform capabilities and Authentication.

---

### erp_accounts

Account and tenancy management.

---

### erp_users

User management.

---

### erp_workers

Background processing.

---

### erp_inventory

Inventory management.

---

## Future Repositories

Potential future repositories:

- erp_billing
- erp_sales
- erp_crm
- erp_hr
- erp_pos
- erp_reports

---

## Infrastructure Repositories

Possible future infrastructure repositories:

- erp-infra
- erp-terraform
- erp-monitoring

---

## Repository ↔ Taiga Relationship

ERP Plus planning does not happen inside repositories.

Repositories are implementation units.

Planning is managed through Taiga.

---

### Source of Truth

| Concern         | Platform |
| --------------- | -------- |
| Roadmap         | Taiga    |
| Sprint Planning | Taiga    |
| User Stories    | Taiga    |
| Tasks           | Taiga    |
| Bugs            | Taiga    |
| Source Code     | GitHub   |
| Pull Requests   | GitHub   |
| Releases        | GitHub   |

---

### Internal Development Flow

```txt
Taiga User Story
        ↓
Branch Creation
        ↓
Implementation
        ↓
Pull Request
        ↓
Review
        ↓
Merge
```

### External Contributions

External contributors may contribute without Taiga access.

Typical flow:

```text
GitHub Issue
        ↓
Pull Request
        ↓
Maintainer Review
        ↓
Optional Taiga linkage
```

This allows ERP Plus to remain open to contributions while preserving internal planning governance.
