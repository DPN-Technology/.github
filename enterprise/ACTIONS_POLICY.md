# DPN Enterprise GitHub Actions Policy

## Default

- GitHub Actions enabled for DPN organizations that use CI/CD.
- Default `GITHUB_TOKEN` permissions: read-only.
- Workflow files elevate permissions only where a job requires them.
- External actions use immutable commit SHAs.
- Checkout uses `persist-credentials: false` unless a documented Git write is required.
- `permissions: write-all` is prohibited.
- Self-hosted runners are treated as privileged infrastructure.

## Workflow execution protections

Enterprise Actions policies now support protections based on actor and event. DPN should explicitly control:
- who may trigger workflows;
- whether `workflow_dispatch` is permitted;
- whether `pull_request_target` is permitted;
- behavior for GitHub Apps, Dependabot, automation identities and contributors.

DPN target:
- allow `push`, `pull_request`, `merge_group`, `schedule`, and approved `workflow_dispatch`;
- disallow `pull_request_target` by default;
- grant exceptions only to reviewed workflows with a threat model.

## Third-party Actions

Preferred order:
1. GitHub-owned actions.
2. Approved security/open-source actions pinned to commit SHA.
3. DPN-owned reusable workflows.
4. Unreviewed third-party actions only after explicit review.

## Reusable workflows

The public `DPN-Technology/.github` repository is the DPN workflow control plane. Enterprise and organization rulesets should call the dedicated Enterprise ruleset workflow, while repositories may call reusable workflows for product-specific needs.

## Runners

If DPN introduces self-hosted runners:
- separate trusted/private builds from untrusted/public PR workloads;
- use runner groups;
- avoid persistent secrets on runner hosts;
- prefer ephemeral runners for high-risk workflows;
- monitor runner registration and job history.
