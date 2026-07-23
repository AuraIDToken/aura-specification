# APS-200 — Canonical Data Model

Document ID: APS-200  
Version: 1.0-DRAFT  
Status: DRAFT  
Classification: Normative Specification  
Authority: APS-001 · APS-100  
Last Review: 2026-07-23

---

## 1. Purpose

APS-200 defines the canonical data model of the Aura Protocol.

Every conformant implementation MUST represent information in accordance with this document. Internal structures MAY differ, but data semantics and contract MUST be equivalent.

---

## 2. Design Principles

The data model MUST be:
- **Deterministic** — same data → same representation
- **Unambiguous** — no field has multiple valid interpretations
- **Extensible** — new fields MAY be added without breaking existing contracts
- **Versionable** — every object carries version information
- **Language-independent** — the model is not tied to any programming language
- **Serialization-independent** — the model is not tied to any wire format

---

## 3. Core Entities

| ID | Entity | Description |
|----|--------|-------------|
| ENT-001 | Protocol Header | Execution metadata |
| ENT-002 | Evaluation Request | Input data |
| ENT-003 | Evaluation Result | Output of evaluation |
| ENT-004 | Policy Reference | Reference to the policy used |
| ENT-005 | Evidence | Execution proof |
| ENT-006 | Attestation | Formal conformance confirmation |
| ENT-007 | Audit Record | Immutable auditable event record |
| ENT-008 | Implementation Metadata | Information about the implementation |

---

## 4. Common Object Contract

Every entity MUST contain the following fields:

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| `object_id` | string | MUST | Globally unique identifier (UUID v4 or canonical format) |
| `object_type` | string | MUST | APS-000 canonical type name (e.g., `EvaluationRequest`) |
| `protocol_version` | string | MUST | APS version this object conforms to (e.g., `1.0`) |
| `schema_version` | string | MUST | Schema version of this entity definition |
| `created_at` | string (ISO 8601) | MUST | Timestamp of object creation (UTC) |
| `integrity_hash` | string | MUST | SHA-256 hash of the canonical serialization of this object |

---

## 5. Entity Definitions

### ENT-001 — Protocol Header

**Purpose**: Carries metadata about a single protocol execution.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `execution_id` | string | MUST | Unique identifier for this execution |
| `implementation_id` | string | MUST | Identifier of the implementation (see ENT-008) |
| `policy_reference` | ENT-004 | MUST | Policy used in this execution |
| `started_at` | string (ISO 8601) | MUST | Execution start timestamp (UTC) |
| `completed_at` | string (ISO 8601) | MUST | Execution completion timestamp (UTC) |

> **TODO**: Define `execution_id` format precisely.

---

### ENT-002 — Evaluation Request

**Purpose**: The input to a protocol execution.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `input_hash` | string | MUST | SHA-256 hash of the canonical input payload |
| `input_schema` | string | MUST | Identifier of the input schema version |
| `request_fields` | object | MUST | Validated, schema-conformant input payload |

> **TODO**: Define the canonical schema for `request_fields`.

---

### ENT-003 — Evaluation Result

**Purpose**: The output of a protocol execution.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `execution_id` | string | MUST | References ENT-001 `execution_id` |
| `decision` | string | MUST | Canonical decision value (e.g., `ALLOW`, `DENY`, `MEASURE`) |
| `output_hash` | string | MUST | SHA-256 hash of the canonical output payload |
| `policy_reference` | ENT-004 | MUST | Policy used to produce this result |

> **TODO**: Define the canonical set of `decision` values.

---

### ENT-004 — Policy Reference

**Purpose**: Identifies the policy used in an execution.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `policy_id` | string | MUST | Unique identifier for the policy |
| `policy_version` | string | MUST | Version of the policy |
| `policy_hash` | string | MUST | SHA-256 hash of the policy content |

---

### ENT-005 — Evidence

**Purpose**: Cryptographically verifiable proof of execution.

See APS-300 for the full Evidence Model. The canonical Evidence object fields are defined in APS-300 §5.

---

### ENT-006 — Attestation

**Purpose**: Formal confirmation of conformance.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `attestation_type` | string | MUST | Type (e.g., `CONFORMANCE`, `EXECUTION`) |
| `attested_execution_id` | string | MUST | The execution_id this attests |
| `evidence_reference` | string | MUST | object_id of the Evidence Pack |
| `attestation_hash` | string | MUST | SHA-256 hash of attestation content |

> **TODO**: Define the full Attestation lifecycle and authority.

---

### ENT-007 — Audit Record

**Purpose**: Immutable record of a single auditable event.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `event_type` | string | MUST | Canonical event type |
| `sequence_number` | integer | MUST | Monotonically increasing sequence number within a session |
| `previous_record_hash` | string | MUST | Hash of the previous Audit Record (chain link) |
| `event_payload_hash` | string | MUST | Hash of the event payload |

---

### ENT-008 — Implementation Metadata

**Purpose**: Identifies and describes a specific implementation.

| Field | Type | Requirement | Description |
|-------|------|-------------|-------------|
| Common Object Contract fields | — | MUST | See §4 |
| `implementation_id` | string | MUST | Canonical ID (e.g., `RI-PY`, `RI-RS`) |
| `implementation_name` | string | MUST | Human-readable name |
| `implementation_version` | string | MUST | Semantic version of the implementation |
| `aps_version` | string | MUST | APS version this implementation claims conformance with |
| `conformance_report_id` | string | SHOULD | Reference to Conformance Report |

---

## 6. Relationships

```
Evaluation Request (ENT-002)
        │
        ▼
Evaluation Result (ENT-003)
        │
        ▼
Evidence (ENT-005)
        │
        ▼
Attestation (ENT-006)
        │
        ▼
Audit Record (ENT-007)
```

Every relationship MUST be traceable via object_id references.

---

## 7. Validation Rules

Every object MUST pass:
1. Structure validation (required fields present)
2. Type validation (field types match schema)
3. Required field validation
4. Integrity validation (integrity_hash matches computed hash)
5. APS-100 invariant validation

---

## 8. Serialization Requirements

Implementations MAY use different formats (JSON, CBOR, Protocol Buffers), provided:
- Full model semantics are preserved
- Deterministic serialization is guaranteed where required by the protocol
- INV-003 (Canonical Serialization) is not violated

> **TODO**: Define the canonical serialization format for interoperability between RI-PY and RI-RS.

---

## 9. JSON Schema

> **TODO**: Publish JSON Schema definitions for each entity at a stable URL. Schemas belong in `fixtures/schemas/`.

---

## 10. Traceability

| Entity | Related Invariants | Related Evidence | Related CONF |
|--------|-------------------|-----------------|--------------|
| ENT-001 | INV-009, INV-015 | EVID-CORE | CONF-008 |
| ENT-002 | INV-001, INV-003 | EVID-CORE | CONF-001, CONF-003 |
| ENT-003 | INV-001, INV-003, INV-013 | EVID-CORE | CONF-001, CONF-003 |
| ENT-004 | INV-013 | EVID-CORE | — |
| ENT-005 | INV-004, INV-005, INV-011 | EVID-CORE | CONF-004, CONF-009 |
| ENT-006 | INV-005 | EVID-CONF | CONF-005 |
| ENT-007 | INV-012 | EVID-AUDIT | — |
| ENT-008 | INV-009, INV-015 | EVID-CORE | CONF-008 |

---

*Source: Original text preserved in [`APS-200 — Canonical Data Model_260723_192852.txt`](../APS-200%20%E2%80%94%20Canonical%20Data%20Model_260723_192852.txt)*
