# Documentation Contribution Guide

This document defines how documentation is created, reviewed, and maintained within ERP Plus.

---

## Purpose

Documentation is considered part of the product.

Changes to the platform should be reflected in documentation whenever applicable.

---

## Documentation Principles

ERP Plus documentation should be:

- accurate
- concise
- maintainable
- versioned
- reviewable

---

## When Documentation Is Required

Documentation updates are required when:

- introducing a new engine
- modifying architecture
- changing workflows
- changing deployment procedures
- introducing new security requirements
- creating an ADR

---

## Documentation Types

### System Documentation

Describes:

- platform behavior
- governance
- architecture

---

### Development Documentation

Describes:

- workflows
- standards
- testing practices

---

### Operations Documentation

Describes:

- deployment
- environments
- rollback procedures

---

### Product Documentation

Describes:

- planning
- sprint execution
- releases

---

## Writing Guidelines

Use:

- short paragraphs
- clear headings
- consistent terminology

Prefer:

```txt
User Story
```

instead of multiple alternative names.

---

## Markdown Guidelines

Use:

```md
# Page Title

## Section

### Subsection
```

Avoid skipping heading levels.

---

## Internal Links

Prefer relative links.

Example:

```md
→ [System Overview](../system/index.md)
```

---

## ADR Rules

Architectural changes should be documented using:

```txt
ADR-XXXX
```

and based on:

```txt
adr-template.md
```

---

## Review Requirements

Documentation changes should be reviewed when they affect:

- architecture
- security
- deployment
- governance

---

## Release Requirements

Before a documentation release:

- links should be validated
- navigation should be validated
- changelog should be updated

---

## Goal

Documentation should remain a reliable source of truth for ERP Plus.
