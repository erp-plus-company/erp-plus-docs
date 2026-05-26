# CI/CD Pipeline

ERP Plus uses GitHub Actions as its CI/CD platform.

---

## Purpose

The pipeline guarantees:

- code quality
- test execution
- security validation
- deployment readiness

---

## Pipeline Flow

```txt
Commit
↓
Pull Request
↓
CI Validation
↓
Review
↓
Merge
↓
Release
↓
Deploy
```

## Validation Stages

### Rubocop

Checks code style consistency.

### RSpec

Runs automated tests.

### Brakeman

Runs security analysis.

### Build Validation

Ensures the application can be built successfully.

---

## Branch Behavior

### develop

- validation only
- no production deployment

### main

- release branch
- production deployment source

---

## Success Criteria

A Pull Request is considered valid only when:

- CI passes
- tests pass
- security scans pass
- review is approved
