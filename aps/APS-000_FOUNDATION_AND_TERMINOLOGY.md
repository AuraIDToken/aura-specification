# APS-000 — Foundation & Terminology

Document ID: APS-000  
Version: 1.0-DRAFT  
Status: DRAFT  
Classification: Canonical Foundation Specification  
Authority: AURA Constitution v1.0 (FROZEN)  
Last Review: 2026-07-23

---

## 1. Purpose

APS-000 establishes the common language of the Aura Protocol project.

All normative documents, implementations, and artifacts MUST use the terms defined in this document.

In cases of conflicting definitions, APS-000 takes precedence.

---

## 2. Terminology

### TERM-001 — Aura Protocol
The formal specification defining the technical requirements of the Aura project.

### TERM-002 — Implementation
A program fulfilling the requirements of the Aura Protocol Specification.
An implementation does not define the protocol.

### TERM-003 — Conformance
The state in which an implementation satisfies all applicable APS requirements and Protocol Invariants.

### TERM-004 — Protocol Invariant
A normative property that MUST be preserved in all conformant implementations.

### TERM-005 — Evidence
A collection of data enabling independent verification of protocol execution.

### TERM-006 — Evidence Pack
The canonical set of evidence artifacts assigned to a specific execution or release.

### TERM-007 — Attestation
A formal confirmation of conformance generated in accordance with protocol requirements.

### TERM-008 — Audit Record
An immutable record of a single auditable event.

### TERM-009 — Replay
The ability to re-execute a process with an identical result.

### TERM-010 — Canonical Data Model
The official Aura data model (defined in APS-200).

### TERM-011 — Artifact
Any versioned element of the project.

### TERM-012 — Reference Implementation
An implementation used as a conformance exemplar.

---

## 3. Canonical Naming Convention

Mandatory prefixes:

| Prefix | Meaning |
|--------|---------|
| APS | Aura Protocol Specification |
| INV | Protocol Invariant |
| ADR | Architecture Decision Record |
| ARR | Architecture Review Record |
| RFC | Request for Comments |
| CONF | Conformance Test |
| EVID | Evidence |
| FIX | Reference Fixture |
| REL | Release |
| POL | Policy |
| ENT | Data Model Entity |
| DOC | Documentation |

---

## 4. Identifier Specification

Every identifier MUST be unique. Format: `PREFIX-NNN` (zero-padded to three digits minimum).

Examples: `APS-001`, `INV-001`, `ADR-001`, `CONF-001`, `FIX-001`, `EVID-001`

Identifiers MUST NOT be reused, even after deprecation.

---

## 5. Document Status

| Status | Meaning |
|--------|---------|
| DRAFT | Under development |
| REVIEW | Under Architecture Review |
| APPROVED | Formally approved |
| FROZEN | Immutable |
| DEPRECATED | Being phased out |
| ARCHIVED | Historical record only |

---

## 6. Requirement Levels

Per RFC 2119:

| Term | Meaning |
|------|---------|
| MUST | Unconditional requirement |
| MUST NOT | Unconditional prohibition |
| SHOULD | Strong recommendation |
| SHOULD NOT | Strong recommendation against |
| MAY | Optional |

---

## 7. Canonical Registry

The project maintains a central registry covering:
- Documents
- Protocol Invariants
- ADRs / ARRs / RFCs
- Evidence
- Conformance Tests
- Fixtures
- Releases
- Policies

Each entry contains: Identifier, Version, Owner, Status, Related Documents, Last Review.

See [../invariants/INVARIANT_REGISTRY.md](../invariants/INVARIANT_REGISTRY.md) for the Invariant Registry.

---

## 8. Reserved Terms

The following terms MUST NOT be used as synonyms for Aura concepts:
- Reputation
- Social Score
- Trust Score
- Black Box
- Magic
- Unknown State

Their use may cause misclassification of the system under the EU AI Act.

---

## 9. Traceability

Every requirement MUST be traceable:

```
Requirement
      ↓
Invariant (INV-xxx)
      ↓
Test (CONF-xxx)
      ↓
Evidence (EVID-xxx)
      ↓
Release (REL-xxx)
```

No element SHOULD remain unlinked to its corresponding artifacts.

---

## 10. Compatibility Rules

All documents MUST:
- Use APS-000 terminology
- Use consistent identifiers
- Maintain numbering consistency
- Reference canonical documents

---

## Appendix A — Canonical Prefix Registry

| Prefix | Description |
|--------|-------------|
| APS | Protocol Specification |
| INV | Protocol Invariant |
| ADR | Architecture Decision Record |
| ARR | Architecture Review Record |
| RFC | Request for Comments |
| CONF | Conformance Test |
| FIX | Reference Fixture |
| EVID | Evidence |
| ENT | Data Model Entity |
| REL | Release |
| POL | Policy |
| DOC | Documentation |

---

## Appendix B — Naming Rules

- Document names: `UPPER_SNAKE_CASE` or official title
- Identifiers: `PREFIX-NNN`
- Versions: Semantic Versioning (`MAJOR.MINOR[-STATUS]`)
- One identifier MUST NEVER be reused

---

*Source: Original text preserved in [`AURA Protocol Specification APS-000 — Foundation &_260723_191759.txt`](../AURA%20Protocol%20Specification%20APS-000%20%E2%80%94%20Foundation%20%26_260723_191759.txt)*
