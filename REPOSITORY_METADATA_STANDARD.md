# DPN Repository Metadata Standard

Repository metadata must be useful to both people and automation.

## Required human-readable metadata

Maintained repositories should provide, where applicable:

| Field | Purpose |
| --- | --- |
| Name | Stable product/system identity |
| Description | One-sentence truthful purpose |
| Lifecycle | Concept, Prototype, Development, Preview, Release or Retired |
| Owner | Accountable maintainer/team |
| Security path | How vulnerabilities are reported |
| Support path | Where bugs/support requests go |
| Build/Test | How correctness is verified |
| Release channel | Dev, Beta, Stable or N/A |
| License posture | DPN-owned source plus third-party obligations |

## Recommended machine-readable properties

Where GitHub organization custom properties are available, use a schema equivalent to:

```text
dpn_product
lifecycle
criticality
clearance
component
customer_facing
release_channel
security_tier
```

Suggested values:

- lifecycle: concept, prototype, development, preview, release, maintenance, retired
- criticality: tier-1, tier-2, tier-3, experimental
- clearance: L1-GREEN, L2-YELLOW, L3-RED, L4-PURPLE
- component: application, service, infrastructure, website, library, simulation, agent, documentation
- release_channel: dev, beta, stable, none
- security_tier: baseline, elevated, critical

## Description rule

A repository description should say what the software actually does today. Do not present roadmap capabilities as already implemented.

Preferred structure:

```text
<Product> — <current capability> for <primary use/domain>.
```

## Topics

Use consistent public topics only when they are safe and accurate. Examples include `dpn-technology`, `automation`, `cybersecurity`, `infrastructure`, `developer-tools`, `networking`, `simulation`, and `operations`.

Do not encode confidential customer names, private infrastructure identifiers or clearance-sensitive details into public topics.

## Lifecycle and claims

Visual quality never upgrades maturity by itself. Lifecycle must follow evidence:

- Concept — design intent only.
- Prototype — core behavior demonstrable.
- Development — actively hardened.
- Preview — suitable for limited evaluation.
- Release — versioned artifact plus validation and recovery evidence.
- Maintenance — stable with reduced feature development.
- Retired — no longer actively supported.
