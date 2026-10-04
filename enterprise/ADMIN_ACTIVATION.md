# DPN Enterprise Admin Activation

## Priority -1 — Enterprise Overview
- open the DPN Enterprise **Overview** page;
- choose **Create README** or **Edit**;
- copy the reviewed content from `enterprise/OVERVIEW.md`;
- save the Enterprise README;
- verify the hero/diagram images load from the public DPN `.github` repository;
- repeat this step whenever the canonical overview materially changes.


These controls are defined in source but require an Enterprise Owner to activate them in GitHub's Enterprise settings because the connected GitHub automation does not expose Enterprise administration APIs.

## Priority 0 — Identity and authority
- confirm the minimum necessary Enterprise Owners;
- confirm the DPN-Technology organization is owned by the DPN Enterprise account;
- review organization owners and outside collaborators;
- decide whether enterprise SSO/identity management is required.

## Priority 1 — Repository governance
- create the enterprise custom properties defined in `policy.yml`;
- populate repository classifications from `repositories.yml`;
- create E0 baseline ruleset in Evaluate mode;
- create E1 Elevated and E2 Critical rulesets using property targeting;
- use `.github/workflows/dpn-enterprise-ruleset.yml` as the required-workflow entry point;
- move rulesets to Active after evaluation.

## Priority 2 — Actions
- set default workflow token permission to read;
- configure allowed Actions/reusable workflows;
- configure workflow execution protections;
- block `pull_request_target` unless explicitly reviewed;
- review self-hosted runner policy and runner groups.

## Priority 3 — Programmatic access
- require approval for fine-grained PATs;
- set a maximum PAT lifetime;
- plan migration away from classic PATs;
- review OAuth/GitHub Apps and installation scope.

## Priority 4 — Repository lifecycle
- create repository policy for creation/deletion/transfer/visibility;
- prevent accidental repository transfer out of the Enterprise;
- restrict public repository creation to approved actors if desired;
- enforce naming requirements only after testing existing names.

## Priority 5 — Security
Where GitHub Code Security / Secret Protection is licensed:
- apply security configurations by governance tier;
- enable code scanning, dependency review, secret scanning and push protection;
- use delegated bypass for secret/push protection;
- review security overview centrally.

## Activation evidence
Record screenshots or exported settings after activation and link the evidence from a DPN governance issue or ADR.
