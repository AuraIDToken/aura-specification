# Scripts

This directory contains tooling scripts for traceability validation and repository maintenance.

## Planned Scripts

| Script | Purpose | Status |
|--------|---------|--------|
| `check-traceability.sh` | Verify every INV-xxx has a CONF-xxx; every CONF-xxx has a FIX-xxx | TODO |
| `validate-fixtures.sh` | Validate all FIX-xxx JSON files against APS-200 schemas | TODO |
| `generate-traceability-matrix.py` | Auto-generate TRACEABILITY_MATRIX.md from document metadata | TODO |
| `check-doc-headers.sh` | Verify all normative documents have required metadata headers | TODO |
| `check-ids.sh` | Verify no identifier is reused across INV, CONF, FIX, ADR, RFC | TODO |

## Status

> **TODO**: Scripts are pending finalization of APS-200 schemas and canonical document format.

## Conventions

- All scripts MUST be idempotent
- All scripts MUST exit 0 on success, non-zero on failure
- All scripts MUST print a summary of findings
- Scripts MUST NOT modify specification content
