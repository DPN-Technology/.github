# DPN Technology Engineering Standard

This document defines the organization-level engineering principles used to evaluate DPN projects. Repository-specific standards may be stricter.

## 1. Truthful maturity

A project should identify its maturity accurately:

- **Concept** — intent and scope exist.
- **Prototype** — the core idea is demonstrable.
- **Development** — implementation is actively being hardened.
- **Preview** — external evaluation is reasonable, with limitations documented.
- **Release** — versioned artifacts, known limitations, validation and recovery guidance are available.

Visual polish must not be used as a substitute for maturity evidence.

## 2. Explicit trust boundaries

Privileged actions should identify:

- the actor;
- the resource;
- required authorization;
- approval or policy gates;
- audit evidence;
- failure behavior.

## 3. Observable behavior

Material runtime state should be inspectable through logs, health state, telemetry, events or equivalent evidence.

Static UI labels should not claim runtime state they do not actually measure.

## 4. Recoverable failure

Important systems should document how they:

- degrade;
- isolate faults;
- preserve evidence;
- back up state;
- roll back or restore;
- verify successful recovery.

## 5. Integration contracts

Cross-system integration should prefer explicit APIs, events, schemas, SDKs or other stable contracts instead of hidden implementation coupling.

## 6. Release evidence

A release should identify the source revision, validation performed, artifacts produced, known limitations and an appropriate recovery or rollback path.

See [RELEASE_EVIDENCE.md](RELEASE_EVIDENCE.md).

## 7. Dependency hygiene

Third-party components should be intentional, maintained where practical, compatible with the intended use and documented separately from DPN-owned code.

See [DEPENDENCY_POLICY.md](DEPENDENCY_POLICY.md).
