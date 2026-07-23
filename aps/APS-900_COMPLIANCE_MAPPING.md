# APS-900 — Compliance Mapping

Document ID: APS-900  
Version: 1.0-DRAFT  
Status: DRAFT  
Classification: Normative Governance Specification  
Authority: APS-001 · APS-100 · APS-200 · APS-300 · APS-400 · APS-500  
Last Review: 2026-07-23

---

## 1. Purpose

APS-900 defines the Traceability mechanism for the Aura Protocol.

Every normative requirement MUST be traceable from its source through to proof of its fulfillment.

---

## 2. Objectives

Compliance Mapping provides:
- **Full Traceability** — every requirement traces to evidence
- **Auditability** — independent verification of compliance
- **Consistency** — documentation and implementation alignment
- **Impact Analysis** — change in one document → known impact on others
- **Certification basis** — traceability chain is required for conformance

---

## 3. Mapping Model

```
AURA Constitution
        ↓
APS Requirement (APS-001 through APS-950)
        ↓
Protocol Invariant (INV-xxx)
        ↓
Canonical Data Model Entity (ENT-xxx)
        ↓
Evidence Model (APS-300)
        ↓
Conformance Test (CONF-xxx)
        ↓
Reference Fixture (FIX-xxx)
        ↓
Evidence Pack (EVID-xxx)
        ↓
Reference Implementation
        ↓
Release (REL-xxx)
```

A missing link in this chain is an incomplete compliance path.

---

## 4. Compliance Record

Each requirement has a compliance record:

| Field | Description |
|-------|-------------|
| `compliance_id` | Unique identifier |
| `aps_reference` | APS document and section |
| `invariant_reference` | INV-xxx |
| `data_model_reference` | ENT-xxx |
| `evidence_reference` | EVID-xxx |
| `conformance_test_reference` | CONF-xxx |
| `fixture_reference` | FIX-xxx |
| `implementation_reference` | RI-PY or RI-RS |
| `release_reference` | REL-xxx |
| `compliance_status` | PASS / FAIL / PARTIAL / NOT VERIFIED / DEPRECATED |

---

## 5. Compliance Status

| Status | Meaning |
|--------|---------|
| PASS | Requirement satisfied |
| FAIL | Requirement not satisfied |
| PARTIAL | Partially satisfied |
| NOT VERIFIED | Not yet verified |
| DEPRECATED | Requirement withdrawn |

---

## 6. Impact Analysis

Every APS document change MUST define impact on:
- Protocol Invariants
- Canonical Data Model
- Evidence Model
- Conformance Tests
- Reference Fixtures
- Reference Implementations

---

## 7. Traceability Matrix

Full machine-readable matrix: [../compliance/TRACEABILITY_MATRIX.md](../compliance/TRACEABILITY_MATRIX.md)

Example entries:

| APS | INV | CONF | FIX | EVID | STATUS |
|-----|-----|------|-----|------|--------|
| APS-200 §4 | INV-015 | CONF-003 | FIX-001 | EVID-001 | NOT VERIFIED |
| APS-300 §5 | INV-004 | CONF-004 | FIX-005 | EVID-005 | NOT VERIFIED |
| APS-100 INV-001 | INV-001 | CONF-001 | FIX-001 | EVID-001 | NOT VERIFIED |

---

## 8. Compliance Report

Each implementation generates a Compliance Report containing:
- Protocol version
- Implementation version
- Test results
- Evidence Pack identifiers
- List of satisfied and unsatisfied requirements

Template: [../templates/CONFORMANCE_REPORT_TEMPLATE.md](../templates/CONFORMANCE_REPORT_TEMPLATE.md)

---

## 9. Certification Rules

An implementation MAY be marked Aura Protocol Conformant if:
- All mandatory compliance records have status PASS
- No requirements have status FAIL
- A complete traceability path exists for every requirement

---

## 10. Governance

APS-900 is the reference document for:
- Architecture Reviews
- Compliance Reviews
- Audits
- Certification processes

Every new APS version requires corresponding updates to the Compliance Mapping.

---

*Source: Original text preserved in [`APS-900 — Compliance Mapping_260723_194128.txt`](../APS-900%20%E2%80%94%20Compliance%20Mapping_260723_194128.txt)*
