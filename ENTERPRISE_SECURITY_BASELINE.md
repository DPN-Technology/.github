# DPN Technology — GitHub Enterprise Security Baseline

This baseline defines the organization-level target for DPN repositories on GitHub Enterprise Cloud.

## Control planes

DPN treats repository security as four coordinated layers:

1. **Organization controls** — access, Actions policy, security configurations, auditability and repository rulesets.
2. **Reusable DPN gates** — source-controlled checks from `DPN-Technology/.github`.
3. **Repository-specific CI** — language, build, test, packaging and runtime verification.
4. **Release evidence** — checksums, SBOM/dependency records, attestations, release notes and rollback guidance.

## Default branch ruleset target

For active repositories, target the default branch and require:

- pull requests for changes;
- required status checks before merge;
- conversation resolution;
- deletion protection for the default branch;
- linear history where it does not conflict with repository release practice;
- merge queue for repositories with enough parallel contribution to benefit from it;
- checks that support the `merge_group` event before enabling merge queue.

Recommended required checks, once they report reliably:

- DPN Enterprise Green Gate;
- repository build/test CI;
- CodeQL/code scanning where licensed and enabled;
- dependency review where available;
- repository-specific security or release-integrity checks.

Avoid enabling a required check until the workflow has successfully reported at least once on the target repository.

## GitHub Actions policy

Organization target:

- default `GITHUB_TOKEN` permissions set to read-only;
- workflows elevate permissions only at the job level when required;
- external actions pinned to immutable commit SHAs;
- `persist-credentials: false` for checkout unless a workflow intentionally needs Git write access;
- no `permissions: write-all`;
- privileged triggers such as `pull_request_target` require explicit threat review;
- production deployment credentials stored in protected environments rather than repository files.

## Secret protection

For public repositories, use GitHub's available secret-scanning and push-protection capabilities.

For private/internal repositories, GitHub Secret Protection or GitHub Advanced Security licensing is required for the full private-repository feature set. GitHub Enterprise Cloud by itself does not automatically include all Advanced Security products.

Target configuration when licensed:

- secret scanning enabled;
- push protection enabled;
- generic/AI secret detection enabled where available;
- custom DPN secret patterns for internal token formats;
- delegated bypass rather than unrestricted bypass;
- bypass events reviewed in Security Overview.

## Code security

For public repositories, enable code scanning and dependency review where supported.

For private/internal repositories, GitHub Code Security or GitHub Advanced Security is required for the full private-repository feature set.

Target configuration when licensed:

- dependency graph enabled;
- Dependabot alerts enabled;
- Dependabot security updates enabled;
- dependency review required on pull requests;
- CodeQL default or advanced setup enabled for supported languages;
- repository security configurations managed centrally where practical.

## Release integrity

Release-producing repositories should move toward:

- immutable source revision;
- deterministic or repeatable build steps where practical;
- dependency/license record;
- generated checksums;
- artifact provenance attestations;
- protected release environments for sensitive publishing credentials;
- release notes and rollback/recovery guidance.

## Access and administration

- keep organization base permissions minimal;
- prefer teams and custom repository roles over broad individual admin grants;
- keep repository deletion, ruleset bypass and security administration limited;
- review outside collaborators regularly;
- use least privilege for deploy keys and GitHub Apps.

## DPN enforcement model

The reusable Green Gate supports two modes:

- `audit` — reports enterprise findings without blocking existing repositories;
- `enforce` — fails when enterprise policy violations are present.

Roll repositories from audit to enforce only after their findings are remediated. This prevents an organization-wide hardening rollout from unexpectedly freezing active development.
