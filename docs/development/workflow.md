# Development Workflow

ERP Plus follows a simplified Git flow.

---

## Branches

- main → production
- develop → integration
- feature/\* → new features

---

## Feature workflow

```bash
git checkout develop
git checkout -b feature/my-feature
```

---

## Pull Requests

All PRs must:

- pass CI
- pass Rubocop
- pass tests
- be reviewed

---

## Commit style

We use Conventional Commits:

- feat:
- fix:
- docs:
- ci:
