# Fixtures

This directory contains Reference Fixtures as defined in APS-500.

## Directory Structure

```
fixtures/
├── README.md               This file
├── schemas/                JSON Schema definitions for APS-200 entities
├── core/                   FIX-CORE — baseline operation scenarios
├── boundary/               FIX-BOUNDARY — boundary value testing
├── error/                  FIX-ERROR — error handling
├── replay/                 FIX-REPLAY — replay verification
├── evidence/               FIX-EVIDENCE — Evidence Pack validation
└── compatibility/          FIX-COMPAT — cross-version compatibility
```

## Status

> **TODO**: All canonical fixtures (FIX-001+) are pending finalization of APS-200 entity schemas and APS-300 Evidence Pack format. See [ROADMAP.md](../ROADMAP.md) Milestone 2.

## Fixture Index

| Fixture ID | Name | Category | CONF Test | Status |
|------------|------|----------|-----------|--------|
| FIX-001 | Basic Evaluation | CORE | CONF-001 | TODO |

## Authoring New Fixtures

1. Copy [`../templates/FIXTURE_TEMPLATE.json`](../templates/FIXTURE_TEMPLATE.json)
2. Assign the next sequential `FIX-NNN` identifier
3. Place in the appropriate category subdirectory
4. Link to related CONF-xxx test(s) and INV-xxx invariants
5. Submit via pull request with a reference to the related APS-500 section

## Important Rules

- Fixture IDs are NEVER reused
- A fixture whose Expected Output changes becomes a NEW fixture (new ID)
- Old fixtures are deprecated, not modified
- Fixtures MUST be used unmodified by implementations
