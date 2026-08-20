# Security Assessment

Status: assessment performed for the current release. This document records
the most likely and impactful potential security problems for this project and
the mitigations in place. It is reviewed before each release.

## What this project is

The mcp governance risk framework: a markdown framework (v1.0) mapping mcp governance risks to mitigations, with reference material and review feedback.

## Assets

1. **Content/specification integrity** - the published content must not silently change.
2. **Tool correctness** - any shipped tooling must not be tricked into wrong output.
3. **No foothold from use** - consuming the content or running the tooling must not compromise the user's host.

## Likely and impactful problems

| # | Problem | Likelihood | Impact | Mitigation |
|---|---------|------------|--------|------------|
| Stale governance guidance | Medium | Medium | Versioned framework doc; change policy in CHANGELOG |

## Threat model scope

- **In scope:** content integrity, tooling input handling, release integrity.
- **Explicitly out of scope:** transport security of external endpoints the user chooses to reach.

## Attack surface analysis

- Components: mcp-governance-risk-framework-v1.0.md, framework-mapping.md / reference.md.
- CI workflows: least-privilege `contents: read` permissions (plus scoped `security-events: write` for SAST).
