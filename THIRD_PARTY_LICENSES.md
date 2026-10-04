# DPN Technology .github — Third-Party Components

This repository contains DPN-owned governance documentation and reusable GitHub automation. The reusable workflows rely on externally maintained GitHub Actions for CI, security analysis, artifact handling and provenance.

## CI / governance tooling

Workflow references are pinned to immutable commit SHAs where practical. Human-readable release lines are retained as comments in workflow files.

| Component | Version line | Purpose | Runtime-shipped? |
| --- | --- | --- | --- |
| actions/checkout | v7 | Repository checkout | No |
| actions/upload-artifact | v7 | Evidence/artifact retention | No |
| actions/download-artifact | v8.0.1 | Evidence/artifact retrieval | No |
| actions/attest-build-provenance | v4.2.2 | Build provenance attestation | No |
| github/codeql-action | v4 | SARIF / CodeQL integration | No |
| actions/dependency-review-action | v5.0.0 | Pull-request dependency review | No |
| ossf/scorecard-action | v2.4.4 | OpenSSF repository security posture | No |

These components execute inside GitHub Actions and are **not shipped as DPN application runtime code**.

Each component remains subject to its own upstream license and terms. New workflow dependencies must be reviewed for source, maintenance, permissions, license posture and supply-chain risk before adoption.

## DPN separation rule

DPN-owned governance, workflow composition and policy remain separate from externally maintained Actions. A third-party Action being used by DPN does not make that Action DPN-owned code.
