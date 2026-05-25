# ⏪ Rollback Strategy

This document defines how ERP Plus recovers from failed releases.

---

# Goal

Restore service safely when a deployment introduces problems.

---

# Git Rollback

For code-level rollback:

```bash
git revert <commit>
```

---

# Kamal Rollback

For deployment rollback:

Restore the previous application version through Kamal deployment history.

---

# Rollback Principles

- rollback must be fast
- rollback must be traceable
- rollback must be documented

---

# Production Rule

Every release must have a clear rollback path before deployment.
