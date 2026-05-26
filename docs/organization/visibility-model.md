# Visibility Model

ERP Plus follows a public-by-default documentation model.

---

## Public Information

The following information should be public whenever possible:

- Documentation
- Architecture
- ADRs
- Development workflows
- Contribution guidelines
- Security policy
- Public roadmap

Purpose:

- transparency
- onboarding
- community growth

---

## Private Information

The following information must remain private:

- Secrets
- Production credentials
- Infrastructure credentials
- Internal incidents
- Financial information
- Backup procedures
- Production runbooks

---

## Guiding Principle

If the information helps understand ERP Plus:

→ Public

If the information helps operate production systems:

→ Private

---

## Documentation Policy

Architecture documentation belongs in:

erp-plus-docs

Operational secrets never belong in:

- Git repositories
- Documentation repositories
- Public issue trackers
