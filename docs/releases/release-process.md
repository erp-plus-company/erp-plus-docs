# Documentation Release Process

This document defines the official release workflow used for ERP Plus Documentation.

---

## Core Principle

No documentation release should be published without:

- review
- changelog updates
- version tagging

---

## Release Workflow

```txt
Documentation Changes
        ↓
Review
        ↓
Release Candidate
        ↓
CHANGELOG Update
        ↓
Git Tag
        ↓
Published Release
```

---

## Release Candidate (RC)

Before a release:

- links should be validated
- navigation should be validated
- duplicated content should be removed
- documentation should be reviewed

Example:

```txt
RC1
RC2
RC3
```

---

## Versioning

### Major Release

Used when:

- structure changes significantly
- navigation changes substantially
- documentation strategy changes

Example:

```txt
2.0.0
```

---

### Minor Release

Used when:

- new sections are added
- new documentation is introduced

Example:

```txt
1.1.0
```

---

### Patch Release

Used when:

- fixing typos
- fixing links
- correcting examples

Example:

```txt
1.0.1
```

---

## Changelog Requirement

Every release must update:

```txt
CHANGELOG.md
```

before tagging.

---

## Git Tag Creation

Example:

```bash
git tag -a v1.0.0 -m "ERP Plus Documentation v1.0.0"

git push origin v1.0.0
```

---

## Release Checklist

Before publishing:

- Navigation verified
- Internal links verified
- Changelog updated
- ADR references validated
- Markdown formatting validated

---

## Goal

The release process guarantees:

- documentation stability
- historical traceability
- predictable evolution
