# DPN Technology Reliability Standard

Reliability is an operating contract between users, systems and operators. A service should define what good behavior means, how that behavior is measured, what degraded behavior looks like and how recovery is verified.

## 1. Service objectives

Where reliability materially matters, define one or more service objectives such as:

- availability;
- latency;
- freshness;
- correctness;
- completion rate;
- recovery time;
- recovery point.

Avoid inventing numeric targets before there is enough evidence to justify them. A qualitative objective with a real measurement is better than a precise-looking number with no basis.

## 2. Health signals

A health state should be derived from evidence such as:

- metrics;
- logs;
- traces;
- synthetic checks;
- queue depth;
- dependency state;
- audit events;
- replication or synchronization state.

Static labels like “healthy,” “ready” or “live” should not be used as runtime claims unless they are backed by actual checks.

## 3. Degraded operation

Important systems should define how they behave when dependencies fail.

Examples:

- read-only mode;
- queued writes;
- local cache;
- reduced feature set;
- disabled privileged operations;
- operator approval requirement;
- fail-closed or fail-open behavior, chosen deliberately.

## 4. Error budgets and change velocity

When a system has measurable reliability objectives, use the remaining reliability margin to inform how aggressively changes should be introduced.

The purpose is not bureaucracy. It is to make change risk visible.

## 5. Recovery

Recovery should specify:

- trigger conditions;
- owner or authority;
- rollback/restore mechanism;
- evidence to preserve;
- verification after recovery.

## 6. Learning loop

Reliability incidents should update one or more of:

- tests;
- alerts;
- health checks;
- architecture;
- runbooks;
- objectives;
- capacity assumptions;
- rollback procedures.
