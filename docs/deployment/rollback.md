# Rollback Strategy

This document defines how ERP Plus recovers from failed releases, production incidents, deployment failures, or critical regressions.

Rollback is considered a first-class operational capability.

---

## Purpose

The goal of a rollback is to:

- restore service availability
- minimize customer impact
- preserve system integrity
- maintain deployment traceability

---

## Core Principle

Every production deployment must have a rollback path.

If a deployment cannot be rolled back safely:

> it should not be deployed.

---

## Rollback Governance

Rollbacks are operational actions.

They must be:

- documented
- traceable
- reviewed after execution

---

## Rollback Decision Flow

```text
Incident Detected
        ↓
Impact Assessment
        ↓
Rollback Decision
        ↓
Rollback Execution
        ↓
Verification
        ↓
Incident Review
```

---

## Common Rollback Scenarios

### Application Failure

Examples:

- application crashes
- startup failures
- runtime exceptions
- broken user workflows

---

### Deployment Failure

Examples:

- failed container rollout
- failed migration
- failed release process

---

### Functional Regression

Examples:

- business logic defects
- multi-tenancy issues
- permission problems
- data visibility problems

---

### Security Incident

Examples:

- unauthorized access
- privilege escalation
- exposed functionality

---

## Release Traceability

Every rollback should be traceable to:

### Taiga

- Epic
- User Story
- Issue (if applicable)

### GitHub

- Pull Request
- Merge Commit
- Release

### Deployment

- Kamal deployment
- Environment
- Deployment logs

---

## Git-Based Rollback

For isolated code regressions:

```bash
git revert <commit>
```

Example:

```bash
git revert a1b2c3d
```

After reverting:

```bash
git push origin main
```

The normal deployment workflow should then be executed.

---

## Kamal Rollback

If the issue is deployment-related:

restore the previously known good release using Kamal deployment history.

Example:

```bash
kamal rollback
```

The exact rollback procedure may vary depending on Kamal version and deployment configuration.

Always verify current operational procedures before execution.

---

## Database Considerations

Database rollbacks require special care.

---

### Safe Cases

- additive migrations
- non-destructive schema changes

---

### Risky Cases

- dropped columns
- dropped tables
- destructive data migrations

---

### Rule

Never assume database rollback is automatic.

Migration rollback strategy must be evaluated before deployment.

---

## Production Rollback Workflow

```text
Production Issue
        ↓
Incident Validation
        ↓
Rollback Approved
        ↓
Rollback Executed
        ↓
Health Verification
        ↓
Taiga Incident Updated
        ↓
Postmortem
```

---

## Relationship with Taiga

Every production rollback should generate or update:

### Existing Work Item

- related User Story
- related Issue

or

### New Issue

Examples:

```text
Production Regression
Deployment Failure
Security Incident
Data Integrity Incident
```

This ensures operational history remains visible.

---

## Verification Checklist

After rollback:

### Application

- application starts correctly
- authentication works
- critical workflows operate normally

### Multi-Tenancy

- account isolation remains intact
- permissions behave correctly

### Infrastructure

- containers healthy
- monitoring stable
- background jobs operational

---

## Post-Rollback Actions

After stabilization:

### Required

- identify root cause
- create corrective task
- document lessons learned

### Recommended

- create Taiga Issue
- update ADR if architectural
- improve automated tests

---

## Incident Documentation

Every production rollback should record:

- date
- environment
- release affected
- rollback reason
- corrective actions

---

## Anti-Patterns

Never:

- rollback without validation
- rollback without documenting cause
- deploy a known broken fix immediately after rollback
- skip verification steps

---

## Operational Philosophy

ERP Plus follows:

```text
Deploy Safely
      ↓
Observe
      ↓
Rollback Fast
      ↓
Learn
      ↓
Improve
```

---

## Related Documentation

→ [CI/CD Pipeline](../deployment/ci-cd.md)

→ [Kamal Deployment](../deployment/kamal.md)

→ [Environments](../deployment/environments.md)

→ [Governance & Evolution](../system/governance-and-evolution.md)
