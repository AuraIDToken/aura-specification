# RI-RS — aura-guard

Document ID: RI-RS  
Version: v1.3.0  
Language: Rust  
Repository: https://github.com/AuraIDToken/aura-guard-v1.3  
APS-950 Certification Status: NOT CERTIFIED  
Last Review: 2026-07-23

---

## Role

Deterministic audit middleware. Accepts AI system interactions via HTTP, evaluates against Ed25519-signed YAML policies, produces SHA-256 hash-chained JSONL audit log with optional Merkle batching and RFC 3161 timestamping.

---

## APS-950 Component Status

| Component | Status | Notes |
|-----------|--------|-------|
| RI-001 Protocol Engine | PARTIAL | Decision engine exists; no APS-200 canonical object headers |
| RI-002 Validation Layer | ✅ | validators.rs, normalizer.rs, policy signature verification |
| RI-003 Evidence Generator | PARTIAL | JSONL audit log + hash chain; not APS-300 Evidence Pack |
| RI-004 Conformance Runner | ❌ MISSING | No APS-400 conformance runner |
| RI-005 Fixture Loader | PARTIAL | tests/fixtures/ exists; not APS-500 canonical |
| RI-006 Audit Interface | ✅ | aura-replay, aura-seal CLIs; hash-chained JSONL |
| RI-007 Version Information | ✅ | /version endpoint; Cargo.toml; CHANGELOG |

## APS-950 Repository Requirements

| Requirement | Status |
|-------------|--------|
| /docs | ✅ |
| /spec | ❌ MISSING |
| /tests | ✅ |
| /fixtures | PARTIAL (tests/fixtures/ — not APS-500) |
| /src | ✅ |
| /examples | ✅ |
| /LICENSE | ✅ (MIT) |
| /CHANGELOG | ✅ |
| /README | ✅ |

## Protocol Invariant Coverage

| INV | Status | Evidence |
|-----|--------|---------|
| INV-001 | ✅ | Same input → same decision; no randomness in path |
| INV-002 | ✅ | aura-replay CLI; hash chain verification |
| INV-003 | PARTIAL | JSON; no APS-200 canonical object schema |
| INV-004 | ✅ | Append-only JSONL; halt on write failure |
| INV-005 | PARTIAL | policy_hash logged; no APS requirement traceability |
| INV-006 | ✅ | Pure Rust; #![forbid(unsafe_code)] |
| INV-007 | ✅ | No float in decision path |
| INV-008 | ✅ | exit 78 on bad policy; 503 on log halt |
| INV-009 | PARTIAL | /version endpoint; no cross-artifact version consistency check |
| INV-010 | ❌ | No CONF-xxx tests |
| INV-011 | ✅ | SHA-256 chain; Ed25519 policy signatures; Merkle roots; RFC 3161 |
| INV-012 | ✅ | Append-only JSONL; aura-replay; segment manifests |
| INV-013 | ✅ | Policy pinned by Ed25519; policy_hash logged |
| INV-014 | ❌ | No APS-500 fixture runner |
| INV-015 | ❌ | No APS-000 identifiers in evidence objects |

## Strengths

- Most mature relative to APS-950 requirements
- CHANGELOG, ADRs, CI, deployment artifacts (Docker/systemd/Kubernetes runbooks)
- SBOM generation, dependency auditing (deny.toml)
- Actively maintained (roadmap to v1.6/v2.0)
- `#![forbid(unsafe_code)]` across all binaries

## Key Gaps

- No canonical APS-200 data model objects
- No APS-300 Evidence Pack (JSONL log is functional equivalent only)
- No APS-400 Conformance Runner
- No APS-500 fixtures
