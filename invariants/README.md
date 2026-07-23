# Invariants

This directory contains the canonical Protocol Invariant Registry.

## Documents

| File | Description |
|------|-------------|
| [INVARIANT_REGISTRY.md](INVARIANT_REGISTRY.md) | Full definitions of all 15 invariants with verification methods and traceability |

## Summary

Protocol Invariants are normative properties that MUST be preserved by every conformant implementation. They are defined in APS-100 and detailed here.

| ID | Title | Class | CONF Test |
|----|-------|-------|-----------|
| INV-001 | Deterministic Evaluation | Critical | CONF-001 |
| INV-002 | Bit-Perfect Replay | Critical | CONF-002 |
| INV-003 | Canonical Serialization | Critical | CONF-003 |
| INV-004 | Immutable Evidence | Critical | CONF-004 |
| INV-005 | Evidence Traceability | Critical | CONF-005 |
| INV-006 | Platform Independence | Critical | CONF-006 |
| INV-007 | Zero Float Runtime | Critical | TODO |
| INV-008 | Fail Closed | Critical | CONF-007 |
| INV-009 | Version Consistency | Major | CONF-008 |
| INV-010 | Conformance Completeness | Critical | CONF-009 |
| INV-011 | Cryptographic Integrity | Critical | CONF-010 |
| INV-012 | Auditability | Critical | TODO |
| INV-013 | Policy Determinism | Critical | TODO |
| INV-014 | Reference Compatibility | Critical | TODO |
| INV-015 | Canonical Identity | Major | TODO |

## Adding New Invariants

Per APS-100 §7: New Invariants MUST have a unique ID, a verification method, at least one Conformance Test, and defined required Evidence. Removal requires a new APS-100 version and formal change process.
