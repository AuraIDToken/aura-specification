# APS-400 — Conformance Test Matrix

Document ID: APS-400  
Version: 1.0-DRAFT  
Status: DRAFT  
Classification: Normative Specification  
Authority: APS-001 · APS-100 · APS-200 · APS-300  
Last Review: 2026-07-23

---

## 1. Purpose

APS-400 defines the official set of Conformance Tests that every Aura implementation MUST pass to be considered conformant with the protocol.

---

## 2. Test Categories

| Category | Purpose |
|----------|---------|
| Functional | Correctness of protocol function |
| Determinism | Repeatability of results |
| Replay | Reproducibility of executions |
| Serialization | Conformance with Canonical Data Model |
| Evidence | Correctness of Evidence Pack |
| Integrity | Data integrity verification |
| Security | Security requirement verification |
| Compatibility | Protocol version compatibility |

---

## 3. Test Definition

Every test MUST define:
- **Test ID** (`CONF-NNN`)
- **Name**
- **Purpose**
- **Related APS sections**
- **Related Invariant(s)**
- **Preconditions**
- **Test Procedure**
- **Expected Result**
- **Evidence Required**
- **PASS / FAIL Criteria**

Full test definitions: [../conformance/](../conformance/)

---

## 4. Canonical Test Matrix

| Test ID | Name | Related Invariant | Category | Status |
|---------|------|------------------|----------|--------|
| CONF-001 | Deterministic Evaluation | INV-001 | Determinism | DRAFT |
| CONF-002 | Replay Verification | INV-002 | Replay | DRAFT |
| CONF-003 | Canonical Serialization | INV-003 | Serialization | DRAFT |
| CONF-004 | Evidence Integrity | INV-004 | Evidence | DRAFT |
| CONF-005 | Traceability | INV-005 | Evidence | DRAFT |
| CONF-006 | Platform Independence | INV-006 | Functional | DRAFT |
| CONF-007 | Fail Closed | INV-008 | Security | DRAFT |
| CONF-008 | Version Compatibility | INV-009 | Compatibility | DRAFT |
| CONF-009 | Evidence Completeness | INV-004 · INV-005 | Evidence | DRAFT |
| CONF-010 | Cryptographic Verification | INV-011 | Integrity | DRAFT |

### CONF-001 — Deterministic Evaluation
**Related Invariant**: INV-001  
**Purpose**: Verify that identical inputs produce identical outputs.  
**PASS Criterion**: All output fields are bit-identical across multiple executions with the same input.  
See [../conformance/CONF-001_DETERMINISTIC_EVALUATION.md](../conformance/CONF-001_DETERMINISTIC_EVALUATION.md)

### CONF-002 — Replay Verification
**Related Invariant**: INV-002  
**Purpose**: Verify that an execution can be reproduced from its Evidence Pack.  
**PASS Criterion**: Replayed execution produces identical Evaluation Result.  
See [../conformance/CONF-002_REPLAY_VERIFICATION.md](../conformance/CONF-002_REPLAY_VERIFICATION.md)

### CONF-003 — Canonical Serialization
**Related Invariant**: INV-003  
**Purpose**: Verify that all protocol objects conform to the APS-200 Canonical Data Model schema.  
**PASS Criterion**: All objects pass JSON Schema validation against APS-200 schemas.  
See [../conformance/CONF-003_CANONICAL_SERIALIZATION.md](../conformance/CONF-003_CANONICAL_SERIALIZATION.md)

### CONF-004 — Evidence Integrity
**Related Invariant**: INV-004  
**Purpose**: Verify that Evidence objects cannot be modified without detection.  
**PASS Criterion**: Any modification of an Evidence object causes integrity check failure.  
See [../conformance/CONF-004_EVIDENCE_INTEGRITY.md](../conformance/CONF-004_EVIDENCE_INTEGRITY.md)

### CONF-005 — Traceability
**Related Invariant**: INV-005  
**Purpose**: Verify the full traceability chain from requirement to Evidence.  
**PASS Criterion**: Every Evidence object links to its APS requirement, Invariant, and Execution.  
See [../conformance/CONF-005_TRACEABILITY.md](../conformance/CONF-005_TRACEABILITY.md)

### CONF-006 — Platform Independence
**Related Invariant**: INV-006  
**Purpose**: Verify that results are identical on different hardware platforms.  
**PASS Criterion**: Same Evidence Pack produced on x86 and ARM platforms.  
See [../conformance/CONF-006_PLATFORM_INDEPENDENCE.md](../conformance/CONF-006_PLATFORM_INDEPENDENCE.md)

### CONF-007 — Fail Closed
**Related Invariant**: INV-008  
**Purpose**: Verify that the implementation halts safely on invalid input or policy failure.  
**PASS Criterion**: Implementation enters safe state; no partial output generated.  
See [../conformance/CONF-007_FAIL_CLOSED.md](../conformance/CONF-007_FAIL_CLOSED.md)

### CONF-008 — Version Compatibility
**Related Invariant**: INV-009  
**Purpose**: Verify that APS version, Data Model version, and Evidence schema version are mutually consistent.  
**PASS Criterion**: All version fields in Evidence Pack reference compatible versions.  
See [../conformance/CONF-008_VERSION_COMPATIBILITY.md](../conformance/CONF-008_VERSION_COMPATIBILITY.md)

### CONF-009 — Evidence Completeness
**Related Invariants**: INV-004 · INV-005  
**Purpose**: Verify that the Evidence Pack contains all mandatory components.  
**PASS Criterion**: Evidence Pack contains Evidence Object, Evaluation Result, Policy Reference, Attestation, and Integrity Metadata.  
See [../conformance/CONF-009_EVIDENCE_COMPLETENESS.md](../conformance/CONF-009_EVIDENCE_COMPLETENESS.md)

### CONF-010 — Cryptographic Verification
**Related Invariant**: INV-011  
**Purpose**: Verify that cryptographic hashes in the Evidence Pack are correct and verifiable.  
**PASS Criterion**: All hashes independently computed match stored hashes.  
See [../conformance/CONF-010_CRYPTOGRAPHIC_VERIFICATION.md](../conformance/CONF-010_CRYPTOGRAPHIC_VERIFICATION.md)

---

## 5. Test Results

Each test returns one of:
- **PASS** — requirement satisfied
- **FAIL** — requirement not satisfied
- **NOT APPLICABLE** — test does not apply to this implementation
- **ERROR** — test could not be executed

---

## 6. Conformance Report

After executing all tests, an implementation generates a report containing:
- Implementation identifier (ENT-008 `implementation_id`)
- Protocol version
- List of tests executed
- Results
- Evidence Pack identifier
- Execution date

Template: [../templates/CONFORMANCE_REPORT_TEMPLATE.md](../templates/CONFORMANCE_REPORT_TEMPLATE.md)

---

## 7. Certification Rules

An implementation MAY be marked Aura Protocol Conformant if:
- All mandatory tests return PASS
- No Critical violations exist
- A valid Evidence Pack has been generated
- The applicable APS version is current

---

## 8. Traceability Matrix

```
APS Requirement
      ↓
Protocol Invariant
      ↓
Conformance Test (CONF-xxx)
      ↓
Evidence (EVID-xxx)
      ↓
Release (REL-xxx)
```

Full matrix: [../compliance/TRACEABILITY_MATRIX.md](../compliance/TRACEABILITY_MATRIX.md)

---

*Source: Original text preserved in [`APS-400 — Conformance Test Matrix_260723_193617.txt`](../APS-400%20%E2%80%94%20Conformance%20Test%20Matrix_260723_193617.txt)*
