# DPN Technology Incident Response Model

This is the organization default for technical incidents. Repository-specific runbooks may add concrete actions and contacts.

## 1. Observe

Preserve current state and evidence.

Examples:

- health telemetry;
- audit events;
- logs;
- affected versions;
- timestamps;
- configuration state.

## 2. Detect and triage

Determine:

- what changed;
- affected systems/users;
- current blast radius;
- whether the issue is security-sensitive;
- whether destructive or privileged behavior is still active.

## 3. Contain

Reduce risk while preserving evidence.

Possible actions:

- disable a feature;
- revoke a credential;
- isolate a service/device;
- block a route;
- freeze a deployment;
- move into degraded mode.

Containment should be scoped; avoid destroying evidence unnecessarily.

## 4. Investigate

Build a timeline and identify root cause.

Capture:

- initiating event;
- affected components;
- authorization decisions;
- relevant code/config revisions;
- external dependencies;
- failure propagation.

## 5. Recover

Restore trustworthy state.

Prefer documented recovery paths:

- rollback;
- restore backup;
- rebuild from trusted source;
- rotate secrets;
- re-enroll devices;
- repair corrupted state.

## 6. Verify

Do not assume recovery succeeded.

Verify:

- service health;
- security controls;
- data integrity;
- audit/event flow;
- backups/recovery path;
- no recurrence of the triggering condition.

## 7. Learn and harden

After recovery:

- document root cause;
- update tests;
- update monitoring;
- update runbooks;
- close control gaps;
- update architecture/threat model where appropriate.

## Incident principle

The goal is not simply to return to service. The goal is to return to a **known, explainable and trustworthy state**.
