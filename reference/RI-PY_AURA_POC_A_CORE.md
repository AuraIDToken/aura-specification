# RI-PY — aura-poc-a-core

Document ID: RI-PY  
Version: v3.3  
Language: Python  
Repository: https://github.com/AuraIDToken/aura-poc-a-core-v3.3  
APS-950 Certification Status: NOT CERTIFIED  
Last Review: 2026-07-23

---

## Role

Layer 0 deterministic measurement engine. Computes ARI (Aura Reliability Index) scores via integer-only arithmetic. Does not make decisions — only measures.

---

## APS-950 Component Status

| Component | Status | Notes |
|-----------|--------|-------|
| RI-001 Protocol Engine | PARTIAL | ARI evaluator exists; no APS-200 canonical object headers |
| RI-002 Validation Layer | ✅ | schema validation as circuit breaker |
| RI-003 Evidence Generator | PARTIAL | ETC (Event Trust Certificate) generated; not APS-300 canonical Evidence Pack |
| RI-004 Conformance Runner | ❌ MISSING | No APS-400 conformance runner |
| RI-005 Fixture Loader | ❌ MISSING | No APS-500 fixture support |
| RI-006 Audit Interface | PARTIAL | audit/ module with Merkle; not APS-200 ENT-007 |
| RI-007 Version Information | PARTIAL | pyproject.toml version only; no protocol_version |

## APS-950 Repository Requirements

| Requirement | Status |
|-------------|--------|
| /docs | ✅ |
| /spec | ❌ MISSING |
| /tests | ❌ (tests inside /core) |
| /fixtures | ❌ MISSING |
| /src | ❌ (uses /core) |
| /examples | ❌ MISSING |
| /LICENSE | ✅ (BSL 1.1) |
| /CHANGELOG | ❌ MISSING |
| /README | ✅ |

## Protocol Invariant Coverage

| INV | Status | Evidence |
|-----|--------|---------|
| INV-001 | ✅ | Zero-float, integer-only runtime |
| INV-002 | ✅ | test_bitwise_replay.py |
| INV-003 | PARTIAL | int32 vectors; no APS-200 schema |
| INV-004 | PARTIAL | ETC generated; no immutability enforcement |
| INV-005 | ❌ | No APS/INV references in evidence |
| INV-006 | ✅ | int32 arithmetic eliminates IEEE-754 drift |
| INV-007 | ✅ | Explicitly enforced |
| INV-008 | ✅ | ARI=0 circuit breaker |
| INV-009 | ❌ | No protocol_version in evidence objects |
| INV-010 | ❌ | No CONF-xxx tests |
| INV-011 | PARTIAL | SHA-256 in Merkle; no canonical Evidence hash |
| INV-012 | PARTIAL | audit/ module exists |
| INV-013 | ✅ | Same policy + input → same decision |
| INV-014 | ❌ | No fixture runner |
| INV-015 | ❌ | No APS-000 identifiers in objects |

## Key Notes

- Self-declared FROZEN (v3.3) — this creates a governance challenge as APS gaps require changes
- BSL 1.1 license (not fully open source)
- No CHANGELOG
- Intentionally excludes Layer 1 (cryptographic proof) and Layer 2 (policy decisions)
