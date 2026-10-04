# DPN Enterprise Ruleset Architecture

DPN should use layered rulesets rather than one giant rule applied identically to every repository.

## E0 — Enterprise Baseline

Target: all maintained repositories.

Start in Evaluate, then Active.

Rules:
- block default-branch deletion;
- block force pushes;
- require pull requests;
- require conversation resolution;
- require the DPN Enterprise Ruleset Gate;
- require repository-specific CI where stable;
- require `merge_group` support before merge queue is enabled.

## E1 — Elevated

Target:
`props.governance_tier:elevated`

Additional rules:
- require at least one approval;
- require CODEOWNERS where ownership is defined;
- require current branch before merge where practical;
- require dependency/license evidence;
- require release provenance for distributables.

## E2 — Critical

Target:
`props.governance_tier:critical`

Additional rules:
- require at least one approval;
- require code-owner review;
- restrict bypass actors;
- protect release tags;
- require Green Gate in enforce mode;
- require security/supply-chain checks;
- require provenance/checksums for releases;
- require explicit rollback/recovery evidence for privileged releases.

## E3 — Public Surface

Target:
`visibility:public`

Additional goals:
- no private infrastructure details;
- no secrets or sensitive identifiers;
- security policy present;
- public-safe README and release notes;
- workflow permissions explicit and least privilege.

## Push rules

For private/internal repositories, evaluate push rules that block:
- private-key file names;
- known credential/config files;
- oversized tracked binaries;
- paths that should only contain generated release artifacts.

Do not block an extension or directory globally until the existing estate has been audited for legitimate use.

## Bypass

Bypass is an exception workflow, not a normal development path.

Every bypass should have:
- actor;
- reason;
- affected rule;
- risk owner;
- compensating control;
- expiration/follow-up.
