# Roadmap

This document describes the planned evolution of the Aura Protocol Specification.

It is maintained by the Chief Architect and updated after each Architecture Review.

---

## Current State (v0.1.x — Specification Bootstrap)

| Item | Status |
|------|--------|
| AURA Constitution | ✅ FROZEN |
| APS-000 Foundation & Terminology | 🟡 DRAFT |
| APS-001 Protocol Specification | ❌ TODO |
| APS-100 Protocol Invariants | 🟡 DRAFT |
| APS-200 Canonical Data Model | 🟡 DRAFT |
| APS-300 Evidence Model | 🟡 DRAFT |
| APS-400 Conformance Test Matrix | 🟡 DRAFT |
| APS-500 Reference Fixtures | 🟡 DRAFT |
| APS-900 Compliance Mapping | 🟡 DRAFT |
| APS-950 Ref. Impl. Requirements | 🟡 DRAFT |
| Invariant Registry | 🟡 DRAFT |
| Canonical Fixture Set | ❌ TODO |
| Conformance Runner Spec | ❌ TODO |
| Traceability Matrix | 🟡 DRAFT |

---

## Milestone 1 — APS-001 and Full Review (Target: v0.2.0)

Priority: **Critical** — APS-001 is the missing root normative document.

- [ ] Author APS-001 Protocol Specification
- [ ] Architecture Review of APS-001
- [ ] Align APS-100 through APS-950 authority citations to APS-001
- [ ] Advance APS-000 to Approved status

---

## Milestone 2 — Canonical Data Model and Evidence Pack (Target: v0.3.0)

Priority: **High** — blocking conformance testing.

- [ ] Define APS-200 entity schemas with precise field types and constraints
- [ ] Define APS-300 canonical Evidence Pack schema with exact field names and cryptographic algorithm
- [ ] Publish JSON Schema for all APS-200 entities
- [ ] Publish JSON Schema for APS-300 Evidence Pack
- [ ] Advance APS-200 and APS-300 to Approved status

---

## Milestone 3 — Conformance Test Suite (Target: v0.4.0)

Priority: **High** — enables formal certification.

- [ ] Define CONF-001 through CONF-010 with full test procedures and pass/fail criteria
- [ ] Define FIX-001 through FIX-010 canonical reference fixtures
- [ ] Publish machine-readable fixture format
- [ ] Advance APS-400 and APS-500 to Approved status

---

## Milestone 4 — Compliance Mapping and First Certification (Target: v1.0.0)

Priority: **Medium**.

- [ ] Automate traceability matrix generation
- [ ] Define Compliance Report format
- [ ] Conduct first Architecture Review of reference implementations against full APS
- [ ] Publish first Conformance Reports for RI-PY and RI-RS
- [ ] Advance all APS documents to Approved or Frozen status
- [ ] Release v1.0.0 of aura-specification

---

## Future Considerations

- Binary evidence envelope format
- Cross-language Evidence verifiers
- Formal verification of Protocol Invariants
- APS-600 (TODO — reserved for future use)
- APS-700 (TODO — reserved for future use)
- Kubernetes-style Enhancement Proposal (AEP) process
- Public certification program

---

## Deprecation Schedule

No documents are currently deprecated.

See [VERSIONING.md](VERSIONING.md) for the deprecation policy.
