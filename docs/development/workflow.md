# Development Workflow

This document defines how contributors work inside ERP Plus.

---

# Branch Strategy

## Main Branches

| Branch     | Purpose      |
| ---------- | ------------ |
| main       | Production   |
| develop    | Integration  |
| feature/\* | New features |
| fix/\*     | Bug fixes    |

---

# Creating a Feature

Start from develop:

```bash
git checkout develop
git pull origin develop

git checkout -b feature/my-feature
```

---

# Conventional Commits

ERP Plus uses Conventional Commits.

Examples:

```bash
feat(accounts): add invitation workflow

fix(workers): resolve retry issue

docs(system): improve architecture guide

ci(release): update release workflow
```

---

# Pull Requests

All contributions must go through Pull Requests.

Direct pushes to protected branches are forbidden.

---

# Merge Rules

A Pull Request can only be merged when:

- CI passes
- tests pass
- security checks pass
- review is approved

---

# Related Documents

- feature-lifecycle.md
- pr-standard.md
- testing.md
- standards.md
