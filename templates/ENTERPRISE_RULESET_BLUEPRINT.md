# DPN Enterprise Organization Ruleset Blueprint

Use this blueprint when configuring the DPN organization ruleset in GitHub Enterprise.

## Ruleset: DPN Default Branch Protection

Target:
- all active repositories, with explicit exclusions only when documented;
- default branch only.

Enforcement:
- begin in Evaluate where available while validating coverage;
- move to Active after required workflows report correctly.

Rules:
- restrict deletion of the default branch;
- block force pushes;
- require pull requests before merge;
- require conversation resolution;
- require status checks before merge;
- require workflows to pass before merging;
- use merge queue on repositories that benefit from parallel merge traffic.

Required DPN workflow:
- source repository: `DPN-Technology/.github`;
- workflow: `.github/workflows/dpn-green-gate.yml`;
- supported triggers in caller/ruleset context: `pull_request` and `merge_group`.

Repository-specific required checks should include build/test CI and security checks that are stable and applicable to that repository.

## Ruleset: DPN Push Protection

For private/internal repositories where GitHub Enterprise push rulesets are appropriate, use push rules to block:

- known private-key or credential file paths;
- oversized files that should live in release/artifact storage;
- prohibited generated/vendor directories where the repository policy disallows them;
- dangerous file extensions only when the repository has no legitimate use for them.

Do not create broad path or extension blocks without testing against existing repositories first.

## Bypass

Keep bypass narrow.

A bypass should identify:
- actor;
- reason;
- risk owner;
- compensating control;
- expiration/follow-up.

Do not use permanent blanket bypass as the normal development path.

## Merge queue

Before enabling merge queue, every required Actions workflow must support `merge_group`. The DPN Enterprise Green Gate caller and workflow template include this trigger.

## Required workflow rollout

GitHub Enterprise rulesets can require a workflow from a designated repository to pass before merge. Use the public DPN `.github` control-plane repository as the reusable/ruleset workflow source where appropriate, then add repository-specific checks separately.

## Advanced Security licensing

GitHub Enterprise Cloud and GitHub Advanced Security products are separate licensing layers for private/internal repositories. Only require CodeQL, dependency review, or Secret Protection checks on private/internal repositories after the corresponding product is licensed and enabled.
