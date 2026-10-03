# DPN Technology Release Evidence Standard

A version number is not enough by itself. A strong release should make it possible to understand what was built, from which source, with what verification and with what known limitations.

## Recommended release evidence

### Identity

- version/tag;
- source commit SHA;
- release date;
- target platform(s).

### Verification

- automated test results;
- relevant manual validation;
- build validation;
- security checks performed;
- migration or upgrade checks when applicable.

### Artifacts

When applicable:

- installers;
- archives;
- images/ISOs;
- packages;
- checksums;
- signatures;
- SBOM or dependency inventory.

### Operational information

- installation or upgrade instructions;
- configuration changes;
- known limitations;
- compatibility notes;
- rollback or recovery procedure.

### Security

- notable security changes;
- changed privileges or permissions;
- new network listeners or external integrations;
- new dependencies or third-party components.

## Evidence language

Use precise language:

- **Source verified** means source inspection or static verification occurred.
- **Build verified** means the software was successfully built in the stated environment.
- **Runtime verified** means the relevant runtime behavior was exercised.
- **Release verified** means the release artifact itself was validated.

Do not use one of these labels to imply the others.
