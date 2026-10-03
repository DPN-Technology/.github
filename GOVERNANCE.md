# DPN Technology Engineering Governance

This document describes the default decision model for DPN engineering work. Repository-specific governance may override it.

## Change classes

### Class A — Routine
Low-risk changes with limited blast radius, such as documentation, styling, non-sensitive refactoring or isolated fixes.

Expected evidence:
- focused review;
- relevant tests or manual verification.

### Class B — Material
Changes that affect application behavior, dependencies, persistent data, networking, integrations or deployment.

Expected evidence:
- documented verification;
- architecture or operational notes where appropriate;
- dependency/security review;
- rollback consideration.

### Class C — Privileged / Critical
Changes that affect authentication, authorization, secrets, signing, update trust, infrastructure control, destructive operations or recovery.

Expected evidence:
- explicit threat/risk review;
- least-privilege analysis;
- audit behavior;
- recovery/rollback plan;
- validation in a representative environment before broad rollout.

## Architecture decisions

Material architecture choices should be captured in an ADR when they:

- establish a new system boundary;
- introduce a durable dependency;
- change the trust model;
- create a public API or event contract;
- affect data ownership;
- significantly alter recovery or deployment.

Use [templates/ADR_TEMPLATE.md](templates/ADR_TEMPLATE.md).

## Security-sensitive work

Security-sensitive changes should document:

- protected assets;
- actors and trust boundaries;
- abuse cases;
- authorization decisions;
- audit evidence;
- containment and recovery.

Use [templates/THREAT_MODEL_TEMPLATE.md](templates/THREAT_MODEL_TEMPLATE.md).

## Release readiness

A release should not be promoted solely because CI is green. Review runtime verification, security, documentation, dependency records, artifacts and rollback/recovery evidence.

Use [templates/RELEASE_CHECKLIST.md](templates/RELEASE_CHECKLIST.md).

## Third-party components

Track externally licensed dependencies and assets separately from DPN-owned code.

Use [templates/THIRD_PARTY_LICENSES_TEMPLATE.md](templates/THIRD_PARTY_LICENSES_TEMPLATE.md).
