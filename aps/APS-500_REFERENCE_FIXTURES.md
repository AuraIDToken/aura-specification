# APS-500 — Reference Fixtures

Document ID: APS-500  
Version: 1.0-DRAFT  
Status: DRAFT  
Classification: Normative Test Specification  
Authority: APS-100 · APS-200 · APS-300 · APS-400  
Last Review: 2026-07-23

---

## 1. Purpose

APS-500 defines the canonical set of Reference Fixtures used to validate Aura Protocol implementations.

Every conformant implementation MUST pass tests using these fixtures unchanged.

---

## 2. Objectives

Reference Fixtures provide:
- **Comparability** — all implementations tested against identical data
- **Repeatability** — tests produce identical results over time
- **Deterministic validation** — no ambiguity in pass/fail
- **Certification basis** — fixtures are the foundation of conformance certification

---

## 3. Fixture Structure

Each fixture MUST contain:

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| `fixture_id` | string | MUST | Unique identifier (`FIX-NNN`) |
| `fixture_version` | string | MUST | Semantic version |
| `protocol_version` | string | MUST | Target APS version |
| `description` | string | MUST | Human-readable description |
| `input_data` | object | MUST | Canonical input (APS-200 ENT-002 structure) |
| `expected_output` | object | MUST | Expected Evaluation Result (APS-200 ENT-003 structure) |
| `expected_evidence` | object | MUST | Expected Evidence Pack (APS-300) structure |
| `related_invariants` | array | MUST | List of INV-xxx identifiers |
| `related_conformance_tests` | array | MUST | List of CONF-xxx identifiers |

---

## 4. Fixture Categories

| Category | Purpose |
|----------|---------|
| `FIX-CORE` | Baseline operation scenarios |
| `FIX-BOUNDARY` | Boundary value testing |
| `FIX-ERROR` | Error handling |
| `FIX-REPLAY` | Replay verification |
| `FIX-EVIDENCE` | Evidence Pack validation |
| `FIX-COMPAT` | Cross-version compatibility |

---

## 5. Canonical Fixtures

> **TODO**: Canonical fixture data requires APS-200 entity schemas and APS-300 Evidence Pack format to be finalized before fixtures can be specified. See ROADMAP.md Milestone 2.

### FIX-001 — Basic Evaluation (Placeholder)
**Category**: FIX-CORE  
**Related Test**: CONF-001  
**Related Invariants**: INV-001, INV-014  
**Status**: TODO — input and output schemas pending APS-200 finalization  
See [../fixtures/FIX-001_BASIC_EVALUATION.json](../fixtures/FIX-001_BASIC_EVALUATION.json)

---

## 6. Fixture Versioning

Each fixture carries:
- `fixture_id` — permanent, never reused
- `fixture_version` — semantic version
- `protocol_version` — APS version this fixture targets

A fixture whose Expected Output changes becomes a new fixture with a new ID. Old fixtures are deprecated, not modified.

---

## 7. Validation Rules

An implementation MUST:
- Use fixtures unmodified
- Produce the expected output
- Produce the expected Evidence Pack
- Pass all related Conformance Tests

---

## 8. Traceability

```
Protocol Requirement
        ↓
Protocol Invariant
        ↓
Conformance Test (CONF-xxx)
        ↓
Reference Fixture (FIX-xxx)
        ↓
Evidence Pack
```

---

## 9. Certification

Reference Fixtures are the mandatory basis of the certification process. Failure on a required fixture = failure of the related Conformance Test.

---

## 10. Repository Organization

Fixtures are stored in [`../fixtures/`](../fixtures/):

```
fixtures/
├── README.md
├── schemas/              JSON Schema definitions for APS-200 entities
├── core/                 FIX-CORE fixtures
├── boundary/             FIX-BOUNDARY fixtures
├── error/                FIX-ERROR fixtures
├── replay/               FIX-REPLAY fixtures
├── evidence/             FIX-EVIDENCE fixtures
└── compatibility/        FIX-COMPAT fixtures
```

---

*Source: Original text preserved in [`APS-500 Reference Fixtures_260723_194023.txt`](../APS-500%20Reference%20Fixtures_260723_194023.txt)*
