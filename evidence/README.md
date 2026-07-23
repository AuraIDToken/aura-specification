# Evidence

This directory contains the Evidence Model templates and guidelines, supplementing APS-300.

## Documents

| File | Description |
|------|-------------|
| [EVIDENCE_PACK_TEMPLATE.md](EVIDENCE_PACK_TEMPLATE.md) | Template for authoring an Evidence Pack |
| [EVIDENCE_TYPES.md](EVIDENCE_TYPES.md) | Descriptions of each evidence type (EVID-CORE, EVID-AUDIT, etc.) |

## Evidence Types

| ID | Type | Description |
|----|------|-------------|
| EVID-CORE | Core Evidence | Proof of a single protocol execution |
| EVID-AUDIT | Audit Evidence | Extended audit trail |
| EVID-CONF | Conformance Evidence | Evidence of passing conformance tests |
| EVID-REL | Release Evidence | Evidence linked to a release |
| EVID-CHAIN | Chain Evidence | Links to a previous Evidence entry |

## Key Requirements (APS-300)

Every Evidence object MUST include:
- `evidence_id` — unique identifier
- `protocol_version` — APS version
- `schema_version` — APS-300 schema version
- `implementation_id` — from ENT-008
- `execution_id` — references ENT-001
- `timestamp` — UTC ISO 8601
- `policy_reference` — references ENT-004
- `input_hash` — SHA-256 of canonical input
- `output_hash` — SHA-256 of canonical output
- `evidence_hash` — SHA-256 of this object
- `attestation_reference` — references ENT-006

See [../aps/APS-300_EVIDENCE_MODEL.md](../aps/APS-300_EVIDENCE_MODEL.md) for full specification.
