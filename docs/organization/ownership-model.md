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

## Related Documents

→ [Roles and Responsibilities](../organization/roles-and-responsibilities.md)

→ [Product & Delivery Management](../product/index.md)
