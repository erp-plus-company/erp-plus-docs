# Environments

ERP Plus uses multiple environments throughout the delivery lifecycle.

---

## Development

Purpose:

Local development.

Characteristics:

- local database
- local services
- developer-owned

---

## Staging

Purpose:

Pre-production validation.

Characteristics:

- production-like environment
- integration testing
- release verification

---

## Production

Purpose:

Customer-facing environment.

Characteristics:

- real users
- monitored infrastructure
- protected deployment process

---

## Configuration Management

Configuration is managed using:

- environment variables
- GitHub Secrets
- Kamal configuration

Secrets must never be stored in Git repositories.
