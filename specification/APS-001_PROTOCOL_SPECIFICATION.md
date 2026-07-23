# APS-001 — Aura Protocol Specification

Document ID: APS-001  
Version: 0.1-DRAFT  
Status: TODO  
Classification: Root Normative Specification  
Authority: AURA Constitution v1.0 (FROZEN)  
Last Review: —

---

> **TODO: This document does not yet exist. It is the highest-priority gap in the Aura Protocol Specification. See [ROADMAP.md](../ROADMAP.md) Milestone 1.**

---

## Purpose

APS-001 defines the normative behavioral specification of the Aura Protocol. It is the root authority for:

- APS-100 Protocol Invariants
- APS-200 Canonical Data Model
- APS-300 Evidence Model
- APS-400 Conformance Test Matrix
- APS-500 Reference Fixtures
- APS-900 Compliance Mapping
- APS-950 Reference Implementation Requirements

No implementation may be considered conformant with the Aura Protocol without a complete APS-001.

---

## Sections Required

The following sections MUST be authored. They are placeholders only.

### 1. Protocol Identity and Scope

> **TODO**: Define the exact scope of the protocol. What does "Aura Protocol execution" mean? What are the entry points and exit points of a protocol run?

### 2. Protocol Execution Model

> **TODO**: Define the lifecycle of a single protocol execution. What steps occur, in what order, and what invariants must hold at each step?

### 3. Input Requirements

> **TODO**: Define what constitutes a valid Evaluation Request (APS-200 ENT-002). What fields are mandatory? What validation is required?

### 4. Output Requirements

> **TODO**: Define what constitutes a valid Evaluation Result (APS-200 ENT-003). What fields must be present in every conformant output?

### 5. Policy Model

> **TODO**: Define the Policy Reference (APS-200 ENT-004). How is a policy identified, versioned, and referenced in output? What makes a policy change a versioning event?

### 6. Evidence Generation Requirements

> **TODO**: Define when Evidence MUST be generated. Define the relationship between a protocol execution and its Evidence Pack (APS-300).

### 7. Cryptographic Requirements

> **TODO**: Define the required cryptographic primitives. Which hash algorithm is canonical? What are the requirements for key management?

### 8. Error Handling

> **TODO**: Define the fail-closed behavior. What conditions trigger a halt? What constitutes a "safe state"?

### 9. Conformance Requirements

> **TODO**: Define what it means for an implementation to be "conformant." Reference APS-400 and APS-500.

### 10. Normative References

> **TODO**: List all normative references (AURA Constitution, APS-000, APS-100 through APS-950).

---

## Authoring Notes

When authoring APS-001:
- Every behavioral statement MUST use MUST/SHOULD/MAY per RFC 2119
- Every requirement MUST be traceable to a Protocol Invariant in APS-100
- Every requirement MUST have a corresponding Conformance Test in APS-400
- Do not copy or paraphrase existing implementation behavior — specify from first principles
- Reference the AURA Constitution principles for each design decision
