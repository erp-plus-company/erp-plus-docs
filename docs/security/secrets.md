# Secrets Management

ERP Plus never stores secrets in source control.

---

## Forbidden

Never commit:

- .env
- credentials.yml.enc
- master.key
- API keys
- database passwords

---

## Approved Secret Storage

Production secrets may be stored in:

- GitHub Secrets
- deployment environment variables
- secure secret managers

---

## Secret Rotation

Secrets should be rotated periodically.

Critical credentials must support emergency rotation.

---

## Access Control

Only authorized maintainers should have access to production secrets.
