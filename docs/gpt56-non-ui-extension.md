# GPT-5.6 Sol non-UI event-driven benchmark

This benchmark adds two non-dashboard application types:

- **Procurement Status Assistant:** private order-status commands, trusted
  synthetic upstream webhooks and authorized Adaptive Card actions.
- **On-call Incident Router:** monitoring-event ingestion, event deduplication,
  service/severity routing, acknowledgement, escalation and resolution.

Each synthetic Slack source was created once and migrated independently three
times. All six targets passed 16–24 deterministic scenarios, authenticated and
Origin-protected loopback HTTP transport, exact response checks, idempotency and
deduplication, tampering/refusal tests and exact source state/audit parity.

No live Slack client or Teams tenant package installation was claimed.

## Direct migration statistics

| Archetype | Accepted | Sample costs | Mean | Median | Minimum | Maximum |
| --- | ---: | --- | ---: | ---: | ---: | ---: |
| Procurement Status Assistant | 3 | 317.484040, 372.157300, 371.317840 | **353.653060** | 371.317840 | 317.484040 | 372.157300 |
| On-call Incident Router | 3 | 252.635200, 194.672180, 366.723280 | **271.343553** | 252.635200 | 194.672180 | 366.723280 |

The six-sample direct migration mean is **312.498307 credits**. Its observed
range is 194.672180–372.157300 credits. The coefficient of variation is 21.64%,
which is materially wider than the full-application four-app allocation because
event-driven repair requirements varied substantially by generated sample.

## All-in accounting

| Scope | Credits |
| --- | ---: |
| Six migration samples | 1,874.989840 |
| One-time source creation and maintenance | 300.384180 |
| Shared kit engineering | 27.392840 |
| GPT-5.6 Sol coordinator | 732.373860 |
| Parent supervision and reporting | 324.356020 |
| **All-in measured total** | **3,259.496740** |
| **All-in mean across six migrations** | **543.249457** |

The allocation rule is:

- assign source creation and maintenance to its archetype, amortized over that
  archetype's three migrations;
- split shared kit, coordinator and parent usage equally over all six samples;
- retain every failed and superseded attempt.

Shared usage is:

`27.392840 + 732.373860 + 324.356020 = 1,084.122720`

`1,084.122720 / 6 = 180.687120` per migration.

Procurement:

`353.653060 + (133.123360 / 3) + 180.687120 = 578.714633`

On-call routing:

`271.343553 + (167.260820 / 3) + 180.687120 = 507.784280`

A timed-out Procurement implementation produced no normal usage file. Its exact
native session usage was recovered from the local session meter and remains a
charged **146.504260-credit failed attempt**.

## Broader non-UI average

Combining these six migrations with three accepted samples each for Maintenance
Approvals, Policy Lookup, Delivery Exceptions, API Reservations and
Service-desk Intake gives:

| Patterns | Accepted migrations | Direct worker total | Direct worker mean |
| ---: | ---: | ---: | ---: |
| 7 | 21 | 3,766.439920 | **179.354282** |

The broader number mixes simple command workflows with event-driven
integrations. It is useful for portfolio planning, but the per-pattern figures
are more reliable for estimating a known application shape.

Human discovery, tenant registrations and consent, licences, hosting, durable
storage, external integrations, security, monitoring, rollout and support are
separate non-AI costs. AI credits require a billing-plan conversion before they
can be expressed in GBP.
