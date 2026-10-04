# DPN Enterprise Custom Properties

GitHub Enterprise custom properties should become the targeting language for DPN governance. GitHub supports enterprise-level repository property definitions and can use those properties to target rulesets.

## Required properties

| Property | Type | Purpose |
| --- | --- | --- |
| `dpn_product` | String | Canonical product/system identity |
| `lifecycle` | Single select | Concept → retired lifecycle |
| `governance_tier` | Single select | Critical, elevated, standard, experimental |
| `criticality` | Single select | Operational criticality |
| `clearance` | Single select | DPN information classification |
| `component` | Single select | Application/service/infrastructure/etc. |
| `customer_facing` | Boolean | Whether external users depend on it |
| `release_channel` | Single select | Dev/beta/stable/none |
| `security_tier` | Single select | Baseline/elevated/critical |

## Why this matters

Manual repository lists drift. Property-based targeting lets Enterprise rules follow the repository's role.

Examples:

- `props.governance_tier:critical` → strict branch and release rules.
- `props.customer_facing:true` → stronger release evidence.
- `props.security_tier:critical` → security-owner review and restricted bypass.
- `props.lifecycle:retired` → block new releases and reduce automation.

## Ownership

The Enterprise owns property definitions. Repository actors should not be able to weaken `governance_tier`, `criticality`, `clearance`, or `security_tier` without an approved governance change.
