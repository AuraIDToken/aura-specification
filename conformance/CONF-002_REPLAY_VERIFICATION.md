# CONF-002 REPLAY VERIFICATION

Document ID: CONF-002
Version: 1.0-DRAFT
Status: DRAFT
Classification: Normative Conformance Test
Authority: APS-400
Related Invariant: INV-002
Last Review: 2026-07-23

---

## 1. Purpose

Verify that an execution can be replayed from its Evidence Pack to produce an identical result.

---

## 2. Related APS

- APS-100: INV-002
- APS-400 §4: CONF-002
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

1. Execute a protocol run and capture the Evidence Pack. 2. Using only the Evidence Pack, replay the execution on the same implementation.

---

## 5. Expected Result

Replayed Evaluation Result MUST be byte-identical to the original. output_hash MUST match.

---

## 6. Evidence Required

EVID-CORE, EVID-CHAIN

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
| Test ID | CONF-002 |
| Invariant | INV-002 |
| Related Fixture | FIX-001 (TODO: assign specific fixture) |
| Evidence Type | EVID-CORE, EVID-CHAIN |

---

> **TODO**: Link to specific fixture file once FIX-xxx canonical fixtures are authored.
