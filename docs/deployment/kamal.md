# Kamal Deployment

ERP Plus uses Kamal as the deployment platform for Staging and Production environments.

Kamal is the final delivery layer of the ERP Plus software lifecycle.

---

## Purpose

Kamal provides:

- containerized deployments
- rolling updates
- reproducible releases
- deployment traceability
- rollback support
- simplified infrastructure management

---

## Deployment Governance

Deployments are not triggered directly from feature branches.

Every deployment must originate from the official workflow:

```text
Taiga User Story
        ↓
Feature Branch
        ↓
Pull Request
        ↓
develop
        ↓
Staging Validation
        ↓
Pull Request
        ↓
main
        ↓
Production Deploy
```

---

## Deployment Lifecycle

### Development

Feature implementation occurs on:

```text
feature/TG-123-description
bugfix/TG-123-description
docs/TG-123-description
```

No Kamal deployment should originate from these branches.

---

### Staging Deployment

A change becomes eligible for Staging after:

```text
Feature Branch
      ↓
Merge into develop
```

The corresponding User Story should normally be moved to:

```text
Ready for Test
```

inside Taiga.

The Staging environment exists to validate:

- requirements
- integrations
- multi-tenancy behavior
- deployment readiness

---

### Production Deployment

A change becomes eligible for Production after:

```text
develop
      ↓
Pull Request
      ↓
main
      ↓
Production Deploy
```

After successful deployment:

```text
User Story → Done
```

---

## Deployment Command

Production deployment:

```bash
bin/kamal deploy
```

Typical deployment sequence:

```bash
git checkout main

git pull origin main

bin/kamal deploy
```

---

## Deployment Ownership

Only ERP Plus maintainers may execute:

```bash
bin/kamal deploy
```

Production deployments are considered governance-controlled operations.

---

## Configuration Management

Deployment configuration is provided through:

- GitHub Secrets
- Kamal configuration
- Environment variables

Secrets must never be committed to Git repositories.

---

## Release Traceability

Every deployment should be traceable to:

### Taiga

- Epic
- User Story
- Issue (if applicable)

### GitHub

- Branch
- Pull Request
- Commit history

### Deployment

- Kamal release
- Environment
- Deployment logs

---

## Deployment Safety Rules

Every deployment must satisfy:

### Required

- Pull Request approved
- CI successful
- Security validation passed
- Tests successful

### Forbidden

- Deploying directly from feature branches
- Deploying unreviewed code
- Skipping CI validation
- Bypassing protected branches

---

## Deployment Philosophy

ERP Plus follows:

```text
Build Once
      ↓
Validate
      ↓
Deploy
      ↓
Observe
      ↓
Rollback if necessary
```

---

## Relationship with Taiga

Taiga is the planning layer.

GitHub is the implementation layer.

Kamal is the delivery layer.

```text
Taiga
   ↓
GitHub
   ↓
Kamal
```

Together they provide complete traceability from requirement to production deployment.

---

## Related Documentation

→ [Development Workflow](../development/workflow.md)

→ [Feature Lifecycle](../development/feature-lifecycle.md)

→ [CI/CD Pipeline](../deployment/ci-cd.md)

→ [Environments](../deployment/environments.md)

→ [Rollback Strategy](../deployment/rollback.md)
