# Architecture Overview

ERP Plus is built as a **modular monolith using Rails Engines**.

---

## Principles

- Separation of concerns
- Engine isolation
- Explicit dependencies
- Multi-account design
- Cloud-native deployment

---

## Core Stack

- Rails 8
- PostgreSQL
- Hotwire
- Stimulus
- TailwindCSS
- Solid Queue / Cache / Cable
- Docker + Kamal

---

## Engines

Each domain is an isolated engine:

- erp_core
- erp_accounts
- erp_users
- erp_workers
- erp_inventory
