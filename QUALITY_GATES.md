# DPN Technology Quality Gates

Quality gates exist to turn engineering evidence into explicit promotion decisions.

A gate is not a badge. It is a decision point with evidence, ownership and a known bypass policy.

## Gate 1 — Architecture

Review when the change affects system boundaries, trust, persistent data, external contracts or recovery.

Evidence may include:

- architecture notes or ADR;
- trust-boundary changes;
- data ownership;
- integration contracts;
- deployment/recovery impact.

## Gate 2 — Source

Evaluate source-level quality:

- formatting/linting;
- type/static analysis;
- dependency changes;
- generated files;
- prohibited secrets or sensitive content.

## Gate 3 — Security

Review security-relevant change:

- auth/authz changes;
- secret handling;
- network exposure;
- privileged operations;
- dependency vulnerabilities;
- supply-chain impact.

## Gate 4 — Test

Use the strongest practical verification for the change:

- unit;
- integration;
- runtime smoke;
- browser/UI;
- migration;
- negative/security tests.

A passing unit test does not imply runtime verification.

## Gate 5 — Artifact

For distributable builds, verify:

- source revision;
- artifact identity;
- checksum;
- SBOM/dependency record when applicable;
- signature when applicable.

## Gate 6 — Release

Confirm:

- version/tag;
- release notes;
- known limitations;
- install/upgrade guidance;
- rollback or recovery path.

## Gate 7 — Operate

Post-release evidence should include, where relevant:

- health state;
- logs/events;
- monitoring;
- auditability;
- recovery verification.

## Gate bypass

A bypass should be exceptional and explicit. Record:

- which gate was bypassed;
- why;
- risk owner;
- compensating control;
- expiration or follow-up action.

A silent bypass is not an accepted operating model.
