# DPN Enterprise Effective State

This document records **verified GitHub Enterprise configuration**, not design intent.

The source-controlled policy files describe the target. A control is marked active here only after an Enterprise Owner verifies the corresponding GitHub setting and records evidence.

## Verification status

| Control | Target | Verified effective state | Evidence |
| --- | --- | --- | --- |
| Enterprise Overview README | Published to Enterprise Overview | Pending verification | — |
| Enterprise custom properties | 9 required property definitions | Pending verification | — |
| Repository property assignments | All governed repositories classified | Pending verification | — |
| E0 Baseline ruleset | Evaluate → Active | Pending verification | — |
| E1 Elevated ruleset | Property-targeted | Pending verification | — |
| E2 Critical ruleset | Property-targeted + restricted bypass | Pending verification | — |
| E3 Public Surface ruleset | Public repositories | Pending verification | — |
| Actions default token | Read-only | Pending verification | — |
| Actions event/actor protections | Enterprise policy applied | Pending verification | — |
| Fine-grained PAT policy | Approval + bounded lifetime | Pending verification | — |
| Repository lifecycle policy | Deletion/transfer/visibility governed | Pending verification | — |
| Security configurations | Tiered where licensed | Pending verification | — |

## Evidence standard

For each verified control record:
- verification date;
- verifier;
- GitHub settings location;
- screenshot/export/reference;
- deviations from source policy;
- remediation owner if mismatched.

## Status rule

The DPN Enterprise Overview must not describe an Enterprise-admin control as **ACTIVE** unless this file contains current verification evidence.

Repository workflows and source-controlled controls may be described as implemented or operational when their GitHub Actions evidence supports that claim.
