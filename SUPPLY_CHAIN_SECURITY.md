# DPN Technology Software Supply-Chain Standard

The goal is to preserve a traceable relationship between source, dependencies, build process, release artifact and verification.

## Source

Projects should identify the source revision behind a release artifact.

Recommended controls:

- protected branches where appropriate;
- code review;
- commit/tag provenance;
- restricted release authority.

## Dependencies

Track third-party components separately from DPN-owned code.

Recommended evidence:

- lockfiles or pinned versions;
- dependency inventory/SBOM;
- license record;
- vulnerability review;
- externally sourced asset notices.

See [DEPENDENCY_POLICY.md](DEPENDENCY_POLICY.md).

## Build

Builds should use documented inputs and repeatable steps where practical.

Record:

- source revision;
- target platform;
- build command/process;
- important toolchain versions;
- build identifier.

## Artifact integrity

Release artifacts should use integrity evidence appropriate to their risk:

- checksums;
- signatures;
- provenance/attestation;
- package metadata;
- immutable release references.

## Release

A release record should connect:

**source → build → artifact → version → release notes**

See [RELEASE_EVIDENCE.md](RELEASE_EVIDENCE.md).

## Verification

Consumers/operators should be able to answer:

1. What source produced this?
2. What third-party code/assets are included?
3. Was the artifact modified?
4. Who or what authorized the release?
5. What verification was performed?
6. How can the artifact be rolled back or replaced?
