# DPN Enterprise Ruleset Architecture

DPN uses layered rulesets rather than one giant rule applied identically to every repository.

The machine-readable companion is [rulesets.yml](rulesets.yml).

## E0 — Enterprise Baseline

**Target:** all maintained repositories.

**Required workflow:** `.github/workflows/dpn-enterprise-ruleset.yml`

Start in **Evaluate** and promote to **Active** only after the workflow reports reliably.

Rules:
- block default-branch deletion;
- block force pushes;
- require pull requests;
- require conversation resolution;
- require the DPN Enterprise Baseline Ruleset Gate;
- require repository-specific CI where stable;
- require `merge_group` support before merge queue is enabled.

## E1 — Elevated

**Target filter:** `props.governance_tier:elevated`

**Required workflow:** `.github/workflows/dpn-enterprise-elevated-ruleset.yml`

Additional rules:
- require at least one approval;
- require CODEOWNERS;
- require current branch before merge where practical;
- require dependency/license evidence;
- require explicit workflow permissions;
- require SHA-pinned external Actions;
- require release provenance for distributables.

The E1 workflow calls the shared DPN Enterprise Green Gate in **enforce** mode with the Elevated contract.

## E2 — Critical

**Target filter:** `props.governance_tier:critical`

**Required workflow:** `.github/workflows/dpn-enterprise-critical-ruleset.yml`

Additional rules:
- require at least one approval;
- require code-owner review;
- restrict bypass actors;
- protect release tags;
- require the Green Gate in enforce mode;
- require security/supply-chain checks;
- require dependency/license evidence;
- require explicit workflow permissions;
- require SHA-pinned external Actions;
- require provenance/checksums for releases;
- require explicit rollback/recovery evidence for privileged releases.

The E2 workflow is the strongest DPN source-control gate and should not be activated until current Critical repositories are clean enough to comply without routine bypass.

## E3 — Public Surface

**Target filter:** `visibility:public`

**Required workflow:** `.github/workflows/dpn-enterprise-public-ruleset.yml`

Additional rules:
- security policy present;
- Enterprise PR template present;
- no private infrastructure inventory;
- no secrets or sensitive identifiers;
- workflow permissions explicit and least privilege;
- external Actions SHA-pinned;
- public README/release notes remain safe to publish.

## Property-driven targeting

Enterprise custom properties are the governance selector.

Examples:

```text
props.governance_tier:critical
props.governance_tier:elevated
visibility:public
```

Property definitions are public-safe. Detailed private/internal repository assignments are maintained in a private operational inventory, not in the public `.github` repository.

## Push rules

For private/internal repositories, evaluate push rules that block:
- private-key file names;
- known credential/config files;
- oversized tracked binaries;
- paths that should only contain generated release artifacts.

Do not block an extension or directory globally until the existing estate has been audited for legitimate use.

## Promotion contract

A ruleset moves from **Evaluate → Active** only after:

1. its required workflow reports reliably;
2. blocking findings are remediated;
3. bypass actors are reviewed;
4. rollback/recovery behavior is understood;
5. source policy matches effective GitHub settings.

## Bypass

Bypass is an exception workflow, not a normal development path.

Every bypass should have:
- actor;
- reason;
- affected rule;
- risk owner;
- compensating control;
- expiration/follow-up.
