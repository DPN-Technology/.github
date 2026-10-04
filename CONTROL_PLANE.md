# DPN Technology GitHub Control Plane v3

The DPN GitHub organization is managed as an engineering control plane, not just a collection of repositories.

## Objectives

The control plane establishes organization-wide defaults for:

- repository identity and maturity;
- engineering evidence and quality gates;
- security and dependency hygiene;
- release evidence and provenance;
- reusable CI/CD;
- public-safe product discovery;
- operational integration with DPN systems.

## Planes

### Policy plane
Defines governance, security, data handling, dependency, release and reliability standards.

### Automation plane
Reusable workflows implement consistent checks without copying large workflow definitions into every repository.

### Evidence plane
Pull requests, workflow results, release metadata, checksums, SBOMs and runbooks provide verifiable evidence.

### Product plane
Each repository remains responsible for its product-specific build, tests, runtime validation and release behavior.

### Integration plane
GitHub events may be consumed by DPN Operational Control, WatchTower, Service Desk or other DPN systems through authenticated, explicitly scoped integrations.

## Repository classes

| Class | Meaning | Default control level |
| --- | --- | --- |
| Experimental | Exploration or proof of concept | Baseline |
| Development | Active product engineering | Standard |
| Preview | External evaluation with documented limits | Elevated |
| Release | Versioned distributable software | Production |
| Critical | Privileged control, identity, security or infrastructure | Restricted |

## Minimum repository contract

A maintained DPN repository should identify its purpose, lifecycle, accountable owner, support path, security reporting path, build/test instructions when applicable, third-party dependency/license record when applicable, and release/recovery expectations when distributable.

See [REPOSITORY_METADATA_STANDARD.md](REPOSITORY_METADATA_STANDARD.md).

## Green Gate

The DPN Green Gate is the organization-wide health model for repository readiness. It does not replace product testing. It combines repository hygiene, evidence, security and release readiness into a visible decision model.

See [GREEN_GATE_STANDARD.md](GREEN_GATE_STANDARD.md).

## Ruleset target model

When organization administration supports centralized rulesets, DPN should maintain layered enforcement:

1. **Baseline** — protect default branches and require successful checks.
2. **Production** — require review, current branches and release evidence.
3. **Critical** — restrict bypass, protect release tags and require security/ownership review.

Rulesets should target repository properties rather than manually maintained repository lists where possible.

## Public/private boundary

The public `.github` repository must never become an inventory of private systems.

Do not publish private repository lists, customer or employee information, internal network topology, credentials, signing material, private incident details, or unverified production-readiness claims.

## Integration direction

Future GitHub-to-DPN integration should follow an authenticated event contract between GitHub and DPN Operational Control, WatchTower, or Service Desk. Every integration must define authentication, authorization, replay handling, audit evidence, failure behavior and secret rotation.


## Deployment patterns

DPN supports two Green Gate deployment patterns:

- **Central reusable gate** — preferred where repository Actions policy allows organization-hosted reusable workflows.
- **Self-contained gate** — permitted where repository visibility, Actions policy, or runner constraints prevent central workflow execution.

Both patterns should preserve the same evidence contract and use read-only permissions unless a specific capability requires more.

A failed workflow that never receives a runner is an infrastructure or policy failure, not evidence that product code failed. Green Gate reporting should distinguish execution failures from repository-evidence failures.


## Enterprise layer

The DPN GitHub control plane now has an explicit Enterprise layer above the organization.

The source-controlled Enterprise design lives in [enterprise/README.md](enterprise/README.md) and includes:

- machine-readable Enterprise policy;
- governance-tier classification for the DPN repository estate;
- enterprise custom-property definitions;
- property-targeted ruleset architecture;
- GitHub Actions execution and supply-chain policy;
- identity/access and programmatic-token posture;
- security configuration rollout;
- an activation checklist for settings that require an Enterprise Owner.

### Layering

```text
DPN Enterprise
  -> enterprise policies / properties / rulesets
    -> DPN-Technology organization
      -> shared .github control plane
        -> repository Green Gate + product CI + security
          -> release provenance and operational evidence
```

The Enterprise layer owns the minimum floor. Organization and repository controls may become more restrictive but should not silently weaken Enterprise policy.
