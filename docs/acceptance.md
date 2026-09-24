# Fresh portfolio acceptance run

On 24 September 2026, the portfolio controller generated new versions of the
policy bot, delivery-exception bot and manager dashboard from clean, separately
copied source workspaces. All three reached independently verified local output
and named-operator local acceptance. No generated target files were manually
repaired by the coordinating assistant.

This is a new generation run, not a replay of the previously generated Teams
source. It is also **not a new tenant deployment**. Historical live Slack/Teams
evidence is documented separately in `migrations.md`.

## What the workflow actually exercised

- Imported three source jobs, isolated their source snapshots and replayed the
  reviewed source baselines before generation.
- Recorded seven source/scope-backed clarification answers. These are synthetic
  pilot operator decisions, not authenticated customer-owner approval.
- Ran a separately metered policy investigation conversation. An early
  consultation wrote to an unintended in-scope output location; the integrity
  gate rejected it and the exact output-path contract was corrected. Both
  invocations remain in the cost ledger.
- Reviewed all three source-evidenced assessments and approved their exact hashes.
- Used GPT-5.4 mini for assessment, consultation, clarification, implementation
  and every model repair; no more-expensive model was substituted.
- Preserved each original domain service byte-for-byte.
- Policy passed six replay scenarios / 18 transport-variant steps. Delivery
  passed seven / 39. The dashboard passed 12 domain scenarios / 14 steps.
- The default four-attempt implementation limit stopped delivery. The user
  explicitly approved two additional attempts, then two final attempts, without
  changing the model or 1,000-credit budget. Delivery passed on attempt seven;
  the eighth permitted attempt was not used.
- A domain-level dashboard pass did not bypass downstream acceptance. Local
  browser review rejected silent malformed-response handling and a disabled
  retry path. The rejection was recorded and routed into its remaining repair
  allowance.
- The repaired dashboard passed five local headless-browser scenarios: normal
  decisions/filtering/refusals/audit plus 401 clearing; malformed list responses;
  malformed decision responses; malformed JSON; and a locked-shell retry with
  fresh Teams context.
- Reconciled every native meter and resumed the accepted portfolio with a guard
  that would fail on any further model invocation. No new model calls occurred.

The browser harness used synthetic TeamsJS context and intercepted HTTP routes
calling the generated domain/adapter. It did not authenticate to a real tenant.

## Managed AI credits

| App | Assessment | Clarification | Consultation | Initial implementation | Repairs | Total |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Policy | 4.651065 | 2.049525 | 3.463665 | 26.967930 | 14.056650 | **51.188835** |
| Delivery | 6.932685 | 3.153735 | 0 | 47.585835 | 32.613375 | **90.285630** |
| Dashboard | 10.294020 | 0 | 0 | 14.852925 | 31.737540 | **56.884485** |
| Total | **21.877770** | **5.203260** | **3.463665** | **89.406690** | **78.407565** | **198.358950** |

The aggregate allowance was 1,000 credits; **801.64105 credits remained**.
Failed attempts and corrective resumes are included. Resumed sessions contribute
only incremental usage, not their cumulative totals again.

These figures include all model activity launched through this portfolio runner,
including its investigation and clarification. They **exclude development of the
kit, the outside coordinating conversation and review, the independent browser
harness, public documentation/site work, staff effort, licences and hosting**.
They are not an all-in project price. Product development and outside
coordination remain a separate cost scope; intermediate native checkpoints must
not be presented as final totals.

The older three mini migrations cost 128.32986 credits under a narrower measured
scope. Do not add those historical costs to this batch's app rows or treat the
difference as a controlled model-performance comparison.

## Controller and release checks

The product suite covers 19 controller cases, including approval integrity,
source boundaries, unknown-cost blocking, incremental metering, interrupted-run
recovery, dependency gating, rejected output, explicit retry overrides, downstream
acceptance rejection, completed-run resumption and the public file allowlist.
The older engine retains its 18 regression checks.

Early product testing found and fixed a dependency-bootstrap scope error,
Windows transient atomic-rename failures and a recovery marker that confused
completed verifier updates with worker tampering. These were controller fixes,
not manual repairs to generated app targets. The original four verified
migrations' source/output/evidence hashes remained intact.

The public page was reviewed at desktop and mobile sizes in light/dark modes,
including filtering, overflow and a network-blocked browser run. Public release
files are selected by an explicit allowlist, not by copying the whole workspace.

## Remaining boundaries

This is a Windows/PowerShell developer preview with two defined recipe families,
sequential execution and local operator labels. It is not an OS sandbox, an
authenticated approval service, a general Slack exporter/converter, a production
deployment system or a guarantee that an arbitrary app will migrate successfully.
Production infrastructure templates were deferred from this release.

The source and generated code, native usage logs, questions, approvals and
browser evidence remain in private run records. This public repository contains
curated documentation and the website only. The toolkit, synthetic source
fixtures, generated apps and ZIP remain private, as do tenant identifiers,
authentication state, private conversations and original screenshots.
