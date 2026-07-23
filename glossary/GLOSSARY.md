# Aura Protocol Glossary

Authority: APS-000  
Version: 1.0-DRAFT  
Last Review: 2026-07-23

---

Canonical definitions for all terms used in the Aura Protocol. Cross-referenced with APS-000.

---

## A

**Artifact** (TERM-011)  
Any versioned element of the Aura project. Every artifact has an identifier, version, owner, and status.

**Attestation** (TERM-007)  
A formal confirmation of conformance generated in accordance with protocol requirements. See ENT-006.

**Audit Record** (TERM-008)  
An immutable record of a single auditable event. See ENT-007.

**Aura Protocol** (TERM-001)  
The formal specification defining the technical requirements of the Aura project. It is a protocol, not an application or AI model.

**ARI** (Aura Reliability Index)  
A deterministic measurement value computed by RI-PY using integer arithmetic. ARI is a measurement, not a decision.

---

## C

**Canonical Data Model** (TERM-010)  
The official Aura data model defined in APS-200. All implementations MUST be semantically equivalent to this model.

**Conformance** (TERM-003)  
The state in which an implementation satisfies all applicable APS requirements and Protocol Invariants.

**Conformance Test** (CONF-xxx)  
A normative test defined in APS-400 that an implementation MUST pass to be considered conformant.

---

## E

**Evidence** (TERM-005)  
A collection of data enabling independent verification of protocol execution. Evidence is immutable once generated.

**Evidence Pack** (TERM-006)  
The canonical set of evidence artifacts assigned to a specific execution. Minimum contents: Evidence Object, Evaluation Result, Policy Reference, Attestation, Integrity Metadata.

---

## F

**Fail Closed** (Constitutional Principle 6)  
In the absence of valid input or valid policy, execution MUST halt safely. No partial output is permitted.

---

## I

**Implementation** (TERM-002)  
A program fulfilling the requirements of the Aura Protocol Specification. An implementation does not define the protocol.

**Invariant** → See *Protocol Invariant*

---

## P

**Protocol Invariant** (TERM-004)  
A normative property that MUST be preserved in all conformant implementations. Defined in APS-100, detailed in the Invariant Registry.

---

## R

**Reference Implementation** (TERM-012)  
An implementation used as a conformance exemplar. Defined in APS-950.

**Replay** (TERM-009)  
The ability to re-execute a process with an identical result. See INV-002.

---

## Reserved Terms (MUST NOT use as Aura synonyms)

Per APS-000 §8, the following terms MUST NOT be used as synonyms for Aura concepts:

| Prohibited Term | Reason |
|-----------------|--------|
| Reputation | Implies accumulation/profiling — prohibited by design |
| Social Score | Same as above |
| Trust Score | Implies probabilistic assessment — Aura is deterministic |
| Black Box | Opposite of Aura's transparency goal |
| Magic | Implies undocumented behavior |
| Unknown State | All states must be explicit |

Use of these terms may cause misclassification under the EU AI Act.
