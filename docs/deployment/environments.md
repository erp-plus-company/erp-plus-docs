# Environments

ERP Plus uses multiple environments throughout the software delivery lifecycle.

The promotion of changes across environments follows the official ERP Plus workflow:

```text
Taiga User Story
        ↓
Feature Branch
        ↓
Pull Request → develop
        ↓
Ready for Test
        ↓
Validation in Staging
        ↓
Pull Request → main
        ↓
Done
        ↓
Production Deployment
```

---

## Environment Strategy

ERP Plus currently defines three primary environments:

| Environment | Purpose                     |
| ----------- | --------------------------- |
| Development | Local feature development   |
| Staging     | Validation and testing      |
| Production  | Customer-facing environment |

---

## Development

### Purpose

Local development environment used by contributors and maintainers.

### Characteristics

- local database
- local services
- developer-owned configuration
- feature implementation
- task execution linked to Taiga User Stories

### Source Branches

Typically:

```text
feature/*
bugfix/*
docs/*
```

Examples:

```text
feature/TG-123-user-invitations
bugfix/TG-88-stock-calculation
docs/TG-33-localizacion-onboarding
```

---

## Staging

### Purpose

Pre-production validation environment.

### Characteristics

- production-like configuration
- integration testing
- QA validation
- User Story verification

### Promotion Rules

A change reaches Staging after:

```text
Feature Branch
      ↓
Pull Request
      ↓
Merge into develop
```

At this point the related User Story should be moved to:

```text
Ready for Test
```

inside Taiga.

### Goals

Validate:

- business requirements
- engine behavior
- multi-tenancy rules
- deployment readiness

---

## Production

### Purpose

Customer-facing environment.

### Characteristics

- real users
- monitored infrastructure
- protected deployment process
- controlled releases

### Promotion Rules

A change reaches Production after:

```text
develop
     ↓
Pull Request
     ↓
main
     ↓
Deploy
```

The corresponding User Story should be moved to:

```text
Done
```

after successful deployment.

---

## Configuration Management

Configuration is managed using:

- environment variables
- GitHub Secrets
- Kamal configuration

Secrets must never be stored in Git repositories.

---

## Governance Rules

Environment promotion must always remain traceable through:

- Taiga User Stories
- Pull Requests
- Git history
- CI/CD pipeline logs

Every production change should be traceable back to a User Story, Issue, or Epic.

---

## Environment Lifecycle

```text
Development
      ↓
Staging
      ↓
Production
```

No deployment should bypass this flow.

---

## Related Documentation

→ [CI/CD Pipeline](../deployment/ci-cd.md)

→ [Kamal Deployment](../deployment/kamal.md)

→ [Rollback Strategy](../deployment/rollback.md)

→ [Development Workflow](../development/workflow.md)
