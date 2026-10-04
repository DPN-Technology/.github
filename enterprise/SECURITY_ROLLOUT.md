# DPN Enterprise Security Rollout

## Stage 1 — Inventory
- classify every repository;
- identify public/private/internal visibility;
- inventory existing CodeQL, dependency review, secret scanning and release workflows;
- identify legacy failing gates before enforcement.

## Stage 2 — Baseline
- adopt Enterprise Green Gate everywhere;
- require explicit workflow permissions;
- pin third-party Actions;
- require SECURITY.md;
- add PR evidence template;
- add third-party dependency/license record where applicable.

## Stage 3 — GitHub security configuration
Where licensed and supported:
- dependency graph;
- Dependabot alerts;
- Dependabot security updates;
- dependency review;
- CodeQL/code scanning;
- secret scanning;
- push protection;
- custom secret patterns;
- delegated bypass.

## Stage 4 — Release trust
For distributable repositories:
- build from protected source;
- checksum outputs;
- generate artifact attestations;
- preserve dependency/SBOM evidence;
- protect publishing environments;
- document rollback.

## Stage 5 — Enforce
- switch clean repositories from audit to enforce;
- activate property-targeted rulesets;
- restrict bypass;
- require stable security checks.

## Stage 6 — Continuous governance
- review audit log and API insights;
- review app and PAT access;
- review ruleset bypass events;
- review inactive repositories and stale permissions;
- periodically test restore/recovery paths.
