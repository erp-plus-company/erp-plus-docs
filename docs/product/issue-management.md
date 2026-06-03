# Issue Management

ERP Plus uses Taiga Issues to manage bugs, feedback, support requests, and feature proposals.

Issues may originate from:

- customers
- internal stakeholders
- QA teams
- developers
- product owners

---

## Core Principle

Not every request starts as a User Story.

Most work begins as an Issue.

```txt
Issue
   ↓
Analysis
   ↓
User Story (optional)
   ↓
Task
   ↓
Implementation
```

---

## Issue Sources

### Customer Feedback

Examples:

- usability improvements
- workflow requests
- reporting requests

---

### Bug Reports

Examples:

- application errors
- incorrect calculations
- permission problems

---

### Internal Improvements

Examples:

- technical debt
- refactoring proposals
- architecture improvements

---

## Issue Lifecycle

```txt
New
  ↓
Under Review
  ↓
Accepted
  ↓
User Story Created (optional)
  ↓
Sprint Planning
  ↓
Implementation
  ↓
Closed
```

---

## Classification

Issues should be categorized as:

### Bug

Unexpected behavior.

Example:

```txt
Inventory quantity not updating correctly.
```

---

### Feature Request

New functionality.

Example:

```txt
Allow exporting inventory reports to Excel.
```

---

### Improvement

Enhancement of existing functionality.

Example:

```txt
Improve search performance.
```

---

### Technical

Engineering work.

Example:

```txt
Upgrade authentication service.
```

---

## Priority Levels

ERP Plus uses four priority levels.

### Critical

Production impact.

### High

Business impact.

### Medium

Important but not blocking.

### Low

Future improvement.

---

## Relationship With User Stories

Some Issues become User Stories.

Example:

```txt
Issue:
Customer requests inventory export

        ↓

User Story:
As an inventory manager,
I want to export inventory reports
so that I can analyze stock externally.
```

Not all Issues require a User Story.

---

## Ownership

Every Issue must have:

- a responsible owner
- a priority
- a current status

Unassigned Issues should not enter a Sprint.

---

## Goal

Issue management ensures that customer feedback, bugs, and internal improvements become visible, traceable work.
