# Style Guide

Document ID: POL-STY-001  
Version: 1.0-DRAFT  
Authority: AURA Constitution Article IV (Principle 8: Explicit over Implicit)

---

## 1. Purpose

This guide defines formatting and writing conventions for all documents in `aura-specification`. Consistent style ensures that specifications are unambiguous, machine-parseable, and auditable.

---

## 2. File Naming

| Type | Convention | Example |
|------|-----------|---------|
| APS documents | `APS-NNN_TITLE_IN_UPPER_SNAKE.md` | `APS-200_CANONICAL_DATA_MODEL.md` |
| ADRs | `ADR-NNN_SHORT_TITLE.md` | `ADR-001_NO_FLOAT_RUNTIME.md` |
| RFCs | `RFC-NNN_SHORT_TITLE.md` | `RFC-001_EVIDENCE_PACK_FORMAT.md` |
| Invariants | `INV-NNN_SHORT_TITLE.md` | `INV-001_DETERMINISTIC_EVALUATION.md` |
| Conformance Tests | `CONF-NNN_SHORT_TITLE.md` | `CONF-001_DETERMINISTIC_EVALUATION.md` |
| Fixtures | `FIX-NNN_SHORT_TITLE.json` | `FIX-001_BASIC_EVALUATION.json` |
| Policies | `POL-TOPIC-NNN.md` | `POL-VER-001.md` |
| Governance | `UPPER_SNAKE_CASE.md` | `GOVERNANCE.md` |

---

## 3. Document Header

Every normative document MUST begin with a metadata block:

```markdown
# [Document Title]

Document ID: [PREFIX-NNN]
Version: [MAJOR.MINOR-STATUS]
Status: [DRAFT | REVIEW | APPROVED | FROZEN | DEPRECATED]
Classification: [Normative | Informative | Governance]
Authority: [Parent document(s)]
Last Review: [YYYY-MM-DD]
```

---

## 4. Requirement Language

Use RFC 2119 keywords, always in UPPER CASE:

| Keyword | Meaning |
|---------|---------|
| MUST | Unconditional requirement |
| MUST NOT | Unconditional prohibition |
| SHOULD | Strong recommendation |
| SHOULD NOT | Strong recommendation against |
| MAY | Optional |

Never use "should" or "must" in lower case in normative text.

---

## 5. Identifier Format

All identifiers follow `PREFIX-NNN` format using the canonical prefix registry (APS-000 Appendix A):

- `APS-NNN` — Specification document
- `INV-NNN` — Protocol Invariant
- `CONF-NNN` — Conformance Test
- `FIX-NNN` — Reference Fixture
- `EVID-NNN` — Evidence
- `ADR-NNN` — Architecture Decision Record
- `RFC-NNN` — Request for Comments
- `ENT-NNN` — Data Model Entity
- `REL-NNN` — Release

Numbers are zero-padded to three digits minimum (e.g., INV-001, not INV-1).

---

## 6. Section Numbering

Use decimal section numbering in all normative documents:

```
1. Introduction
2. Terminology
3. Requirements
   3.1 Field Definitions
   3.2 Constraints
4. Traceability
```

---

## 7. Tables

Use Markdown tables for structured data. Every table MUST have a header row. Column headers MUST be descriptive. Use `|---|` alignment rows.

---

## 8. Status Badges

Documents at the top level of the repository SHOULD display a status badge:

```markdown
![Status: DRAFT](https://img.shields.io/badge/status-DRAFT-yellow.svg)
```

---

## 9. TODOs

Missing specification content MUST be marked explicitly:

```markdown
> **TODO**: [Brief description of what is missing and why it is blocked]
```

Never omit a TODO with placeholder text that implies content is present when it is not.

---

## 10. Change Records

Every PR that modifies a normative document MUST update:
1. The `Last Review` date in the document header
2. The `CHANGELOG.md` entry
3. Any affected traceability links in `compliance/TRACEABILITY_MATRIX.md`

---

## 11. Diagrams

- Diagrams MUST be stored in `/diagrams/`
- Preferred format: `.mermaid` or `.svg`
- Every diagram file MUST have a companion `.md` file describing it
- ASCII art diagrams in documents are acceptable for simple flows

---

## 12. Language

- English only in all normative documents
- Polish is acceptable in governance commentary and meeting notes
- Normative text (MUST/SHOULD/MAY) MUST be in English regardless
