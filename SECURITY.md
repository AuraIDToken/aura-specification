# Security Policy

## Scope

This repository contains **documentation only** — no executable code.

Security considerations for this repository are:
1. Integrity of canonical specification documents
2. Authenticity of signed releases
3. Accuracy of security-relevant protocol requirements

## Reporting Specification Security Issues

If you identify a security vulnerability in the **Aura Protocol specification itself** (e.g., a flaw in a cryptographic requirement, an underspecified invariant that could be exploited), please report it privately before publishing.

**Do NOT open a public GitHub issue for security vulnerabilities.**

Contact: open a confidential GitHub Security Advisory in this repository, or email the Chief Architect directly.

Include:
- Which APS section contains the vulnerability
- Which Protocol Invariant(s) are affected
- The nature of the risk
- A proposed remediation (if known)

## Response Process

1. Acknowledgement within 72 hours
2. Assessment and classification within 14 days
3. Draft RFC or errata published within 30 days
4. Affected APS sections revised per Amendment Procedure (AURA Constitution Article XI)

## Out of Scope

Security issues in the **reference implementations** (`aura-poc-a-core`, `aura-guard`) should be reported to their respective repositories.
