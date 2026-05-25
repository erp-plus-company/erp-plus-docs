# 🚢 Kamal Deployment

ERP Plus uses Kamal for application deployment.

---

# Purpose

Kamal provides:

- containerized deployments
- rolling updates
- zero-downtime deployments
- simplified operations

---

# Environment Injection

Deployment configuration is injected through:

- GitHub Secrets
- environment variables
- Kamal configuration

---

# Deployment Flow

```bash
bin/kamal deploy
```

---

# Responsibilities

Kamal handles:

- image distribution
- container orchestration
- application rollout

---

# Benefits

- simple infrastructure model
- reproducible deployments
- rollback support
- production safety
