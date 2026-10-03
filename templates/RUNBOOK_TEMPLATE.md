# Operational Runbook

## Service

- **Name:**
- **Owner:**
- **Environment:**
- **Dependencies:**

## Purpose

What does this service do and who depends on it?

## Normal health

List the signals that show normal operation.

| Signal | Normal state | Where to check |
| --- | --- | --- |
| | | |

## Common failure modes

### Failure mode 1

- Symptoms:
- Likely causes:
- Safe checks:
- Corrective action:
- Escalation threshold:

## Degraded mode

What capability remains available when normal operation is not possible?

## Isolation

How can the service or dependency be safely isolated?

## Backup / restore

- Backup location:
- Backup frequency:
- Restore procedure:
- Restore verification:

## Rollback

How is a bad deployment/configuration reverted?

## Security incident notes

What actions preserve evidence? Which actions should not be performed before escalation?

## Recovery verification

- [ ] Health returned
- [ ] Dependencies healthy
- [ ] Audit/logging functioning
- [ ] Data integrity checked
- [ ] Backups/recovery path checked
- [ ] Trigger condition no longer present

## Escalation

Who owns the next decision if the runbook does not restore a trustworthy state?
