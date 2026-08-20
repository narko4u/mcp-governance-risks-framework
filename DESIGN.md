# Design: mcp-governance-risks-framework

This document describes the design of the MCP Governance Risk Framework: a Markdown framework (v1.0) mapping MCP governance risks to mitigations, with reference material and review feedback: the actors, the actions
they perform, and the data flow. It accompanies
[THREAT-ASSESSMENT.md](THREAT-ASSESSMENT.md) (threat model) and
[TESTING.md](TESTING.md) (test policy).

## Purpose

The mcp governance risk framework: a markdown framework (v1.0) mapping mcp governance risks to mitigations, with reference material and review feedback.

## Actors

| Actor | Description |
| --- | --- |
| Framework reader | Applies the MCP governance risk framework to their MCP deployments. |
| Framework steward | Maintains framework-mapping.md, reference.md, and feedback docs. |

## Actions

| Action | Performed by | Implemented in |
| --- | --- | --- |
| Apply framework | Framework reader | `mcp-governance-risk-framework-v1.0.md` |
| Review framework | Steward / reviewer | `framework-review-feedback.md` |

## Data flow

```
repository (main branch)
        │
        ▼
CI (on push / pull_request) ──► validate / test / security jobs
        │
        ▼
tagged release ──► build artifacts + CycloneDX SBOM + Sigstore signatures + SHA256SUMS
```

## Design invariants

1. **Open by construction.** The content is freely licensed and version-controlled.
2. **Minimal dependencies.** Fewer dependencies means a smaller attack surface.
3. **Tamper-evident releases.** Where releases exist, assets carry Sigstore signatures and checksums.
