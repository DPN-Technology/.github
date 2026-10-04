# DPN Technology Pull Request

## Change summary
Describe what changed and why.

## Change class
- [ ] Class A — routine / low risk
- [ ] Class B — material behavior, dependency, data, network, integration or deployment change
- [ ] Class C — privileged / critical security, identity, secrets, signing, infrastructure or recovery change

## Verification
- [ ] Relevant automated tests pass
- [ ] Build or syntax validation completed where applicable
- [ ] Runtime/manual validation completed where applicable
- [ ] Documentation updated for behavior, setup or architecture changes

## Security and supply chain
- [ ] No credentials, private keys, tokens or customer data are included
- [ ] New dependencies are justified and license-compatible
- [ ] THIRD_PARTY_LICENSES / notices updated when applicable
- [ ] Workflow permissions remain least-privilege
- [ ] External GitHub Actions are pinned to immutable commit SHAs where practical

## Operational impact
- [ ] Rollback or recovery path is understood
- [ ] Logging/monitoring impact reviewed
- [ ] Configuration or migration changes are documented

## Evidence
Link test output, screenshots, logs, release evidence, threat model, ADR, or other proof as appropriate.

## Enterprise gate
This pull request is expected to satisfy the DPN Green Gate plus any repository-specific required checks before merge.
