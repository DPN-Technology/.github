# DPN Technology Dependency & Third-Party Policy

DPN-owned source and externally licensed components should remain clearly distinguishable.

## Selection principles

Prefer third-party components that are:

- actively maintained;
- appropriate for the intended environment;
- suitable for commercial use when the project may be commercially deployed;
- documented well enough to operate and update safely;
- replaceable without requiring a full system rewrite.

## License records

Projects should maintain a third-party dependency/license record such as:

- `THIRD_PARTY_LICENSES.md`;
- `THIRD_PARTY_NOTICES.md`;
- an SBOM;
- or another explicit dependency inventory.

The record should identify the dependency, version or version range, license, source and purpose when practical.

## New dependencies

Before adding a dependency, consider:

1. Is it actually needed?
2. What capability does it provide?
3. What is its maintenance posture?
4. What license applies?
5. Does it introduce native binaries, network access, telemetry or privileged behavior?
6. How difficult would it be to replace?
7. Does it materially expand the attack surface?

## Bundled assets and generated content

Fonts, icons, images, models, media and generated artifacts can carry license obligations too. Track them when redistribution rights are not obvious.

## Security updates

Critical dependency vulnerabilities should be evaluated promptly. A version bump should still be validated against project behavior; security updates are not exempt from regression risk.
