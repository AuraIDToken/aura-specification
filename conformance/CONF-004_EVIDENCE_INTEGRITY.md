# CONF-004 EVIDENCE INTEGRITY

Document ID: CONF-004
Version: 1.0-DRAFT
Status: DRAFT
Classification: Normative Conformance Test
Authority: APS-400
Related Invariant: INV-004
Last Review: 2026-07-23

---

## 1. Purpose

Verify that any modification of an Evidence object is detectable.

---

## 2. Related APS

- APS-100: INV-004
- APS-400 §4: CONF-004
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

Generate an Evidence Pack. Modify one byte in the Evidence object. Re-run integrity check.

---

## 5. Expected Result

Integrity check MUST fail. The original unmodified Evidence MUST pass integrity check.

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
| Test ID | CONF-004 |
| Invariant | INV-004 |
| Related Fixture | FIX-001 (TODO: assign specific fixture) |
| Evidence Type | EVID-CORE |

---

> **TODO**: Link to specific fixture file once FIX-xxx canonical fixtures are authored.
