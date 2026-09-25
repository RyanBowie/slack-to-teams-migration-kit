# GPT-5.6 Sol migration cost benchmark

On 25 September 2026, nine fresh migrations were accepted from unchanged
synthetic Slack sources: three Equipment Loans applications, three Store
Operations applications and three Manager Approvals dashboards.

Every Equipment Loans and Store Operations output passed 14 independent browser
scenarios and a native Teams personal-tab lifecycle with exact Slack
business-state and audit parity. Every Manager Approvals output passed nine
browser scenarios and native approve, reject, refusal and audit parity,
including rejection of a reused one-use access ticket.

## Direct migration-worker costs

| Application type | Accepted samples | Mean | Median | Minimum | Maximum | Worker total |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Equipment Loans | 3 | 295.095800 | 318.381940 | 242.487520 | 324.417940 | 885.287400 |
| Store Operations | 3 | 314.773827 | 287.960180 | 265.559020 | 390.802280 | 944.321480 |
| Manager Approvals | 3 | 238.386000 | 224.466840 | 206.930620 | 283.760540 | 715.158000 |
| **Total** | **9** |  |  |  |  | **2,544.766880** |

Assessment, initial implementation and every metered repair are included.
Failed and superseded attempts were not removed from the ledger.

## All-in AI-credit accounting

| Scope | Credits |
| --- | ---: |
| Migration workers | 2,544.766880 |
| GPT-5.6 Sol coordinators | 2,117.914120 |
| Parent setup, supervision, testing and reporting | 1,941.211250 |
| **All-in measured total** | **6,603.892250** |

The parent total includes **1,370.881050 GPT-6 Astra credits** incurred after
the original approval boundary but before the supervising session was switched,
plus **570.330200 GPT-5.6 Sol credits**. The expensive setup was not reset,
excluded or assigned a zero cost. All new coordinator and worker calls used
GPT-5.6 Sol. Total GPT-5.6 usage in the benchmark was **5,233.011200 credits**.

The frozen meter cutoff is `2026-09-25T21:52:37.417Z`. Static documentation and
GitHub Pages publication after that cutoff launch no migration workers and are
outside this fixed benchmark record.

## Planning allocation

Coordinator usage is shared and was not natively metered per application.
For portfolio planning only, the page divides each coordinator across the app
samples it coordinated and divides parent setup/supervision equally across all
nine accepted migrations:

| Application type | Allocated all-in mean |
| --- | ---: |
| Equipment Loans | 665.143926 |
| Store Operations | 684.821952 |
| Manager Approvals | 851.331539 |

These allocated figures are arithmetic planning values, not independently
metered per-app coordinator charges.

Human effort, licences, subscriptions, infrastructure, durable production
hosting, customer integrations, rollout and support are not AI-credit units and
remain separate project costs.
