# Ownership Model

ERP Plus is designed to support multiple engineering disciplines.

---

## Engineering Roles

### Backend Engineers

Responsibilities:

- Domain logic
- Engines
- APIs
- Data models

---

### Frontend Engineers

Responsibilities:

- User interfaces
- UX implementation
- Client-side integrations

---

### DevOps Engineers

Responsibilities:

- Infrastructure
- Deployments
- Monitoring
- CI/CD

---

### QA Engineers

Responsibilities:

- Validation
- Test strategy
- Regression prevention

---

### Platform Architects

Responsibilities:

- Governance
- Architecture decisions
- Standards
- Platform evolution

---

## Repository Ownership

Example ownership model:

| Repository    | Primary Owner |
| ------------- | ------------- |
| erp_plus      | Platform Team |
| erp-plus-docs | Platform Team |
| erp_accounts  | Backend Team  |
| erp_users     | Backend Team  |
| erp_inventory | Backend Team  |

Ownership may evolve as teams grow.

---

## Decision Authority

Architecture decisions should be documented using ADRs.

No repository should evolve outside documented architecture decisions.

---

---

## Product Ownership & Delivery Governance

ERP Plus uses Taiga as the official planning and delivery platform.

GitHub is the implementation platform.

The relationship is:

```txt
Taiga
 ├── Epics
 ├── User Stories
 ├── Tasks
 ├── Issues
 └── Sprints

            ↓

GitHub
 ├── Branches
 ├── Commits
 ├── Pull Requests
 └── Releases
```

---

## Responsibility Model

### Product Owners

Responsibilities:

- define roadmap
- manage Epics
- prioritize User Stories
- manage sprint planning
- validate delivered functionality

### Engineering Team (Internal Staff)

Responsibilities:

- implement User Stories
- update Task status
- maintain traceability
- participate in sprint execution

Internal contributors have access to:

- Taiga
- GitHub repositories
- CI/CD workflows

### Community Contributors

Responsibilities:

- submit fixes
- improve documentation
- contribute features through Pull Requests

Community contributors do NOT require access to Taiga.

They interact through:

- GitHub Issues
- Pull Requests
- Discussions (future)

Maintainers are responsible for linking external contributions to Taiga work items when necessary.

---

## Sprint Ownership

ERP Plus operates using two-week sprints.

Sprint planning is managed in Taiga.

Each sprint contains:

- User Stories
- Tasks
- Bugs
- Technical improvements

Every deliverable inside a sprint should be traceable to a User Story or Issue.

---

## Traceability Rule

All internal development work must be traceable:

```text
Epic
 └── User Story
        └── Task
               └── Branch
                      └── Pull Request
                             └── Merge
```

This traceability model is part of ERP Plus governance.
