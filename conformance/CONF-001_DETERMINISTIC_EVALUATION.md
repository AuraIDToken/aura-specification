# CONF-001 DETERMINISTIC EVALUATION

Document ID: CONF-001
Version: 1.0-DRAFT
Status: DRAFT
Classification: Normative Conformance Test
Authority: APS-400
Related Invariant: INV-001
Last Review: 2026-07-23

---

## 1. Purpose

Verify that identical inputs produce identical Evaluation Results.

---

## 2. Related APS

- APS-100: INV-001
- APS-400 §4: CONF-001
- APS-300: Evidence requirements
- APS-500: Reference Fixtures

---

## 3. Preconditions

- A conformant implementation is available and running
- Reference fixture FIX-001 (or applicable fixture) is loaded
- No prior state from a different test run exists

> **TODO**: Specify exact preconditions once APS-200 schemas and APS-500 fixtures are finalized.

---

## 4. Test Procedure

Execute the same Evaluation Request (FIX-001 input) twice consecutively with the same policy version.

---

## 5. Expected Result

Both executions MUST produce byte-identical Evaluation Result objects (ENT-003). output_hash values MUST be identical.

---

## 6. Evidence Required

EVID-CORE

---

## 7. PASS / FAIL Criteria

| Outcome | Condition |
|---------|-----------|
| PASS | Expected result achieved with no deviations |
| FAIL | Any required field missing, any hash mismatch, or any deviation from expected result |
| NOT APPLICABLE | Implementation does not support this feature (requires justification) |
| ERROR | Test infrastructure failure — result not recorded |

---

## 8. Traceability

| Field | Value |
|-------|-------|
| Test ID | CONF-001 |
| Invariant | INV-001 |
| Related Fixture | FIX-001 (TODO: assign specific fixture) |
| Evidence Type | EVID-CORE |

---

> **TODO**: Link to specific fixture file once FIX-xxx canonical fixtures are authored.
