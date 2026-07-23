# ADR-001 — Canonical Repository Structure

Document ID: ADR-001  
Status: ACCEPTED  
Date: 2026-07-23  
Author: Documentation Architect  
Related RFC: —  
Supersedes: —  
Superseded By: —

---

## Context

The `aura-specification` repository previously contained only PDF and TXT source files in the root directory with a minimal README. This structure did not support:
- Discoverability of specification documents
- Structured governance workflows (ADR/RFC processes)
- Machine-readable traceability
- Clear separation of specification vs. conformance vs. fixtures vs. governance content

The AURA Constitution requires that "Documentation is Part of the Product" (Principle 10) and that every artifact be versioned, identifiable, and traceable.

---

## Decision

Restructure the repository following the RFC/standards repository model (analogous to IETF, W3C, and Kubernetes Enhancement Proposals).

Create the following directory hierarchy:

```
/constitution   — AURA Constitution
/specification  — APS-001 (root protocol spec)
/aps            — All numbered APS documents
/invariants     — Protocol Invariant Registry
/conformance    — Conformance Test definitions (CONF-xxx)
/fixtures       — Reference Fixtures (FIX-xxx)
/evidence       — Evidence Model templates
/compliance     — Traceability model and matrix
/adrs           — Architecture Decision Records
/rfcs           — Requests for Comments
/reference      — Reference Implementation requirements and status
/glossary       — Canonical terminology index
/diagrams       — Architecture diagrams
/templates      — Document authoring templates
/examples       — Usage examples
/scripts        — Traceability and validation tooling
/releases       — Release artifacts
```

Root-level governance documents: README.md, LICENSE, CODE_OF_CONDUCT.md, CONTRIBUTING.md, SECURITY.md, CHANGELOG.md, ROADMAP.md, VERSIONING.md, STYLE_GUIDE.md, GOVERNANCE.md.

Original source files (PDF + TXT) are preserved in the repository root for provenance.

---

## Rationale

- Matches IETF/W3C/KEP conventions for specification repositories
- Makes navigation of the specification hierarchy unambiguous
- Separates concerns: normative spec, conformance, fixtures, governance, tooling
- Enables automated traceability checks (linking INV → CONF → FIX → EVID)
- Satisfies APS-950 §4 repository structure requirements at the meta level

---

## Consequences

### Positive
- Clear location for every type of artifact
- Governance workflows enabled (ADR/RFC process)
- Traceability matrix becomes maintainable
- Contributors have clear authoring targets

### Negative
- Repository root contains mixed content (legacy .txt/.pdf alongside new .md structure)
- Internal links must be maintained as structure evolves
- APS-001 absence is now structurally visible — this is intentional

### Neutral
- Existing APS source content is re-expressed as canonical Markdown in `/aps/`; original files are preserved

---

## Compliance

| Invariant | Impact |
|-----------|--------|
| INV-015 | Every document now has a canonical identifier and location |
| INV-009 | Version information standardised across all documents |
| INV-005 | Traceability links now structurally encoded |
