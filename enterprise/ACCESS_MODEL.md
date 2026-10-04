# DPN Enterprise Access Model

## Principles

- Enterprise Owner is a governance role, not a routine development permission.
- Repository admin should be exceptional.
- Use teams and custom roles instead of repeated direct grants.
- Separate repository write access from security/ruleset administration.
- Prefer GitHub Apps over long-lived PAT automation.

## Recommended role groups

### Enterprise Owners
Very small set. Can manage Enterprise policies, organizations, billing/governance and Enterprise rulesets.

### Organization Owners
Small set responsible for DPN-Technology administration.

### Security Administrators
Can manage security posture, findings and approved security configuration without becoming universal code owners.

### Repository Maintainers
Manage project settings and releases but cannot weaken Enterprise policy.

### Developers
Write/triage as required by role.

### Read-only / Auditors
Visibility without mutation rights.

## Programmatic access

Target posture:
- require approval for fine-grained PATs;
- define a maximum token lifetime;
- migrate durable automation to GitHub Apps;
- restrict classic PAT access once required automation has migrated;
- inventory OAuth/GitHub Apps periodically.

## Teams

Recommended team model:
- `enterprise-owners`
- `org-admins`
- `security`
- `platform`
- `release-managers`
- product-specific maintainer teams

Names are a design target; do not create duplicate teams if equivalent teams already exist.
