# DPN Technology Data Handling Standard

Data controls should follow the sensitivity, operational value and regulatory obligations of the data being handled.

## Classification

### Public
Information intended for external distribution.

Typical controls:
- integrity review;
- provenance;
- license/attribution checks;
- content approval where applicable.

### Internal
Routine non-public information used for normal operations.

Typical controls:
- authenticated access;
- role-based permissions;
- reasonable retention;
- backup;
- audit for material changes.

### Restricted
Material operational, customer, employee, financial or security-relevant information.

Typical controls:
- least privilege;
- encryption in transit and at rest where practical;
- access logging;
- export restrictions;
- explicit retention;
- recovery controls.

### Sensitive / Secret
Credentials, keys, tokens, recovery secrets, signing material, highly sensitive personal data or other high-impact information.

Typical controls:
- strong authentication;
- segmentation;
- minimal distribution;
- rotation;
- secret-specific storage;
- minimal retention;
- incident response plan.

## Handling questions

Before introducing a new data flow, answer:

1. What data is collected?
2. Why is it needed?
3. Who can access it?
4. Where is it stored?
5. How is it transmitted?
6. How long is it retained?
7. Can it be exported?
8. How is it backed up?
9. How is it deleted?
10. What happens if it is exposed or corrupted?

## Logging

Do not log secrets or unnecessary sensitive values. Prefer stable identifiers, redaction and structured events.

## Test data

Do not use real sensitive production data in tests unless there is a documented and authorized reason. Prefer synthetic or sanitized fixtures.

## Backups

Backup copies inherit the classification of the source data. Protect and expire them accordingly.
