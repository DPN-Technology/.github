# DPN Green Gate Standard

The DPN Green Gate turns engineering evidence into a repeatable repository health decision.

A green status means the defined checks passed for the evaluated scope. It does **not** mean the software is universally secure, bug-free or production-ready.

## Gate domains

| Domain | Typical evidence |
| --- | --- |
| Identity | README, purpose, maturity, owner |
| Source | lint/static analysis, generated-file controls |
| Security | vulnerability path, dependency review, secret hygiene |
| Test | unit/integration/runtime evidence appropriate to the project |
| Dependency | lockfiles/inventory, third-party license record |
| Artifact | build result, checksum/SBOM/signature when applicable |
| Release | version, source revision, notes, limitations, rollback |
| Operations | health signals, logging, runbook/recovery evidence |

## Status model

- **GREEN** — required checks for the repository's declared class passed.
- **YELLOW** — usable for its declared stage but with explicit evidence gaps.
- **RED** — a required control failed or the repository should not be promoted.
- **GRAY** — not evaluated or insufficient information.

## Suggested score

```text
Identity       10
Source         15
Security       20
Test           20
Dependency     10
Artifact       10
Release        10
Operations      5
              ---
              100
```

A critical failure can force RED regardless of score.

## Critical failures

Examples include committed credentials, failed required security checks, unverifiable required release artifacts, missing authorization for privileged behavior, broken recovery for a critical system, or an unrecorded bypass of a required gate.

## Evidence output

Automation should report repository, commit SHA, declared lifecycle, checks performed, checks skipped, failures, and final status.

## Bypass

A bypass should identify the gate, reason, risk owner, compensating control and expiration/follow-up. Silent bypass is not accepted.
