# DPN GitHub Enterprise Rollout

## Phase 1 — Shared control plane

Status target: immediate.

- Upgrade DPN Green Gate with enterprise audit/enforce modes.
- Pin the shared checkout action.
- Add default pull-request security evidence requirements.
- Keep existing repositories in audit mode until findings are known.

## Phase 2 — Organization settings

Configure in GitHub organization/enterprise administration:

- read-only default workflow token permissions;
- organization repository ruleset for default branches;
- required DPN checks after successful first runs;
- merge queue only after `merge_group` support exists;
- security configurations for the repositories covered by any purchased Code Security / Secret Protection licenses;
- protected deployment environments for release-capable repositories.

## Phase 3 — Repository convergence

For every active DPN repository:

- adopt the shared Green Gate;
- remediate audit findings;
- ensure workflow permissions are explicit;
- pin external Actions to immutable SHAs;
- maintain SECURITY.md;
- maintain THIRD_PARTY_LICENSES or equivalent dependency evidence;
- add CODEOWNERS where review ownership is meaningful;
- enable repository-specific CI and security checks.

## Phase 4 — Enforced fleet

After a repository is clean in audit mode:

- switch Green Gate to `enterprise_mode: enforce`;
- enable `require_action_sha_pinning`;
- enable `require_explicit_workflow_permissions`;
- require the Green Gate in the organization ruleset;
- require CodeQL/dependency review where licensed and enabled.

## Phase 5 — Trusted releases

For repositories that publish installers, archives, packages, images or ISOs:

- build from protected source;
- generate checksums;
- generate provenance attestations;
- preserve SBOM/dependency records;
- publish through controlled environments;
- retain release evidence and rollback instructions.

## Rollout principle

A control is not considered deployed because a document mentions it. It is deployed when GitHub settings, source-controlled workflows, required checks and release evidence all agree.
