# DPN Technology — Organization Security Policy

## Reporting a vulnerability

Do not open a public issue for a vulnerability that could expose credentials, sensitive data, infrastructure details, authorization weaknesses, remote execution paths or other exploitable behavior.

Use the affected repository's **Security** tab and private vulnerability reporting when available.

If a repository contains its own `SECURITY.md`, that repository-specific policy takes precedence over this organization default.

## Include

Please provide enough information to reproduce and evaluate the issue:

- affected repository and version/commit;
- affected component or path;
- impact;
- reproduction steps or proof of concept;
- relevant logs or screenshots with secrets removed;
- any suggested mitigation.

## Do not include

- real passwords, tokens, private keys or recovery codes;
- production customer data;
- unrelated personal information;
- destructive testing against systems you do not own or have permission to test.

## Security principles

DPN projects should prefer least privilege, explicit trust boundaries, auditable privileged actions, dependency hygiene, recoverable failure modes and evidence-backed security claims.
