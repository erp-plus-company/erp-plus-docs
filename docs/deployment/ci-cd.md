# CI/CD Pipeline

ERP Plus uses GitHub Actions.

---

## Pipeline

1. Lint (Rubocop)
2. Security scan (Brakeman)
3. Test suite (RSpec)
4. Build Docker
5. Deploy with Kamal

---

## Branch rules

- main → production deploy
- develop → CI only
