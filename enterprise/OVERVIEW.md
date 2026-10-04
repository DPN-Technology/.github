<p align="center">
  <img src="https://raw.githubusercontent.com/DPN-Technology/.github/main/assets/dpn-org-hero.svg" alt="DPN Technology — Develop. Pioneer. Navigate." width="100%">
</p>

# DPN Enterprise // Control Plane

<p align="center">
  <strong>DEVELOP. PIONEER. NAVIGATE.</strong><br>
  Enterprise governance for the DPN Technology engineering estate.
</p>

<p align="center">
  <img alt="Enterprise" src="https://img.shields.io/badge/DPN-ENTERPRISE-E50914?style=for-the-badge&logo=github">
  <img alt="Repositories" src="https://img.shields.io/badge/GOVERNED%20REPOSITORIES-20-111111?style=for-the-badge">
  <img alt="Mode" src="https://img.shields.io/badge/ROLLOUT-AUDIT%20%E2%86%92%20ENFORCE-E50914?style=for-the-badge">
</p>

---

## Enterprise Mission

**DPN Enterprise** is the governance layer above the **DPN-Technology** organization.

Its job is to make engineering policy consistent across the DPN ecosystem while keeping controls proportional to risk. Repository access, workflow execution, required evidence, release trust, security posture, and bypass authority should be governed deliberately rather than independently reinvented by every project.

> **Enterprise policy defines the floor. Organization and repository controls may become stricter, but they should not silently weaken it.**

## Current Control Status

| Control | State | Direction |
| --- | --- | --- |
| Enterprise Overview README | **CANONICAL READY** | Publish this reviewed file from the Enterprise Overview editor |
| Enterprise source of truth | **ESTABLISHED** | Versioned in the public DPN `.github` control plane |
| Repository classification | **20 / 20 BASELINED** | Maintain through Enterprise custom properties |
| Enterprise Green Gate | **OPERATIONAL** | Audit first, enforce after remediation |
| Enterprise Ruleset Gate | **OPERATIONAL** | Designed for centrally required workflows |
| Enterprise custom properties | **DEFINED** | Activate in Enterprise settings |
| E0/E1/E2/E3 rulesets | **DESIGNED** | Evaluate → Active |
| Actions execution policy | **DEFINED** | Activate at Enterprise level |
| Programmatic access policy | **DEFINED** | Enforce PAT/App governance |
| Release provenance | **AVAILABLE** | Expand to all distributable products |
| Security configuration tiers | **ROLLOUT** | Apply where licensed and supported |

## DPN Governance Estate

The Enterprise currently governs **20 repositories** under the DPN Technology organization.

| Governance tier | Repositories | Control intent |
| --- | ---: | --- |
| **Critical** | 8 | Identity, control-plane, privileged, security-sensitive, or sensitive workforce systems |
| **Elevated** | 5 | Infrastructure, operating systems, network/service operations, or business-critical systems |
| **Standard** | 7 | Public surfaces, simulations, games, scripts, and lower-risk applications |
| **Experimental** | 0 | Prototype/exploratory repositories with audit-first controls |

### Clearance distribution

| DPN clearance | Repositories | Enterprise handling |
| --- | ---: | --- |
| **L4 PURPLE** | 3 | Critical-infrastructure governance |
| **L3 RED** | 7 | Restricted engineering / privileged systems |
| **L2 YELLOW** | 2 | Staff/business operations |
| **L1 GREEN** | 8 | Public-safe / general engineering |

Repository names and internal details are intentionally not exposed here unless they are already appropriate for every Enterprise member.

<p align="center">
  <img src="https://raw.githubusercontent.com/DPN-Technology/.github/main/assets/dpn-command-fabric.svg" alt="DPN Command Fabric" width="100%">
</p>

## Enterprise Control Hierarchy

```text
DPN ENTERPRISE
│
├── Enterprise identity + access policy
├── Enterprise custom properties
├── Enterprise rulesets
├── Enterprise GitHub Actions policy
├── Programmatic access / PAT / App policy
│
└── DPN-Technology Organization
    │
    ├── .github Enterprise Control Plane
    │   ├── DPN Enterprise Ruleset Gate
    │   ├── DPN Enterprise Green Gate
    │   ├── Reusable CI
    │   ├── Security / supply-chain workflows
    │   └── Artifact provenance
    │
    └── Product Repositories
        ├── Product-specific CI
        ├── Security evidence
        ├── Dependency/license evidence
        ├── Release evidence
        └── Operational / recovery evidence
```

## Ruleset Stack

| Layer | Target | Enterprise expectation |
| --- | --- | --- |
| **E0 — Baseline** | Maintained repositories | PRs, required checks, conversation resolution, no force-push/deletion |
| **E1 — Elevated** | `governance_tier=elevated` | Approval, ownership, dependency evidence, release provenance |
| **E2 — Critical** | `governance_tier=critical` | Code-owner review, restricted bypass, protected tags, security gates, provenance |
| **E3 — Public Surface** | Public repositories | Public-safe content, security policy, least-privilege workflows, secret hygiene |

The target model uses **Enterprise custom properties** as the ruleset targeting language so policy follows repository purpose instead of relying on fragile hand-maintained repository lists.

## Security + Trust Model

<p align="center">
  <img src="https://raw.githubusercontent.com/DPN-Technology/.github/main/assets/dpn-trust-stack.svg" alt="DPN Trust and Recovery Stack" width="100%">
</p>

DPN Enterprise security is built around:

- least privilege for people, workflows, tokens, Apps, and runners;
- explicit GitHub Actions permissions;
- immutable SHA-pinned third-party Actions;
- protected pull-request and merge paths;
- security and dependency evidence;
- restricted bypass authority;
- checksums and artifact attestations for distributable releases;
- rollback and recovery evidence for privileged changes;
- auditability of policy, exceptions, and promotion decisions.

## Evidence-Driven Engineering

<p align="center">
  <img src="https://raw.githubusercontent.com/DPN-Technology/.github/main/assets/dpn-evidence-chain.svg" alt="DPN Evidence Chain" width="100%">
</p>

A green badge alone is not release evidence. DPN distinguishes:

**source verified → test verified → security verified → artifact verified → release verified → operationally verified**

The Enterprise control plane exists to make that evidence visible and increasingly enforceable.

## Enterprise Quick Access

| Resource | Purpose |
| --- | --- |
| [DPN Technology Organization](https://github.com/DPN-Technology) | Organization and repository estate |
| [Enterprise Control Plane Source](https://github.com/DPN-Technology/.github/tree/main/enterprise) | Versioned Enterprise governance |
| [Enterprise Policy](https://github.com/DPN-Technology/.github/blob/main/enterprise/policy.yml) | Machine-readable control baseline |
| [Repository Classification](https://github.com/DPN-Technology/.github/blob/main/enterprise/repositories.yml) | Governance-tier source of truth |
| [Ruleset Architecture](https://github.com/DPN-Technology/.github/blob/main/enterprise/RULESETS.md) | E0/E1/E2/E3 enforcement model |
| [Actions Policy](https://github.com/DPN-Technology/.github/blob/main/enterprise/ACTIONS_POLICY.md) | Workflow and runner trust model |
| [Access Model](https://github.com/DPN-Technology/.github/blob/main/enterprise/ACCESS_MODEL.md) | Roles, teams, PATs and GitHub Apps |
| [Security Rollout](https://github.com/DPN-Technology/.github/blob/main/enterprise/SECURITY_ROLLOUT.md) | Audit → security configuration → enforce |
| [Enterprise Activation Tracker](https://github.com/DPN-Technology/.github/issues/5) | Enterprise-owner activation work |
| [DPN GitHub Command Center](https://dpn-technology.github.io/) | Public-safe DPN engineering command center |

## Rollout State

### ACTIVE NOW
- source-controlled Enterprise policy;
- repository governance tiers;
- Enterprise Green Gate;
- Enterprise Ruleset Gate;
- reusable organization CI;
- supply-chain/release evidence standards;
- artifact provenance workflow;
- automated control-plane validation.

### ENTERPRISE OWNER ACTIVATION
- create Enterprise custom properties;
- apply property values to repositories;
- enable E0 baseline ruleset in **Evaluate** mode;
- configure Enterprise Actions execution policy;
- configure fine-grained PAT approval/lifetime policy;
- apply security configurations where licensed;
- promote clean repositories from **Audit → Enforce**;
- promote validated rulesets from **Evaluate → Active**.

## Operating Doctrine

**Develop** — build systems with explicit ownership, evidence, and recovery.

**Pioneer** — use Enterprise capabilities to raise the engineering floor without creating useless ceremony.

**Navigate** — measure the estate, surface exceptions, and move controls from advisory to enforced only when evidence says the organization is ready.

---

<p align="center">
  <strong>DPN ENTERPRISE CONTROL PLANE</strong><br>
  <sub>Policy → Identity → Source → Security → Evidence → Release → Recovery</sub>
</p>
