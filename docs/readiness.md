# Installation readiness and migration compatibility

**The private v0.2 kit is reusable, engineer-operated tooling. It is not a
turnkey installer, a universal Slack converter, or a production deployment
service.** This repository contains documentation only: cloning it does not
install the kit, and there is no public toolkit ZIP or finished Teams app here.

The six historical live demonstrations are not six packaged migration recipes.
The stable private archive contains **two recipe families and five synthetic
source fixtures**. Later coverage experiments are documented separately and
must not be mistaken for released functionality.

## What can be migrated

| Pattern | Stable private v0.2 status | Conditions and additional work |
| --- | --- | --- |
| Node/Bolt-style command lookups | Defined `teams-bot-v1` path; latest fresh test failed | Reusable domain service, explicit identity map and reviewed command/response cases. The new policy target did not compile within four attempts; a recipe is not a guarantee of successful generation. |
| Commands with button/action workflows | Same bot recipe | Must fit the command/action contract. Review roles, invalid/repeated/conflicting actions, state and audit; generated Adaptive Cards still need target-client acceptance. |
| Approval-style Slack App Home | Specific `app-home-approvals-v1` path | Requires the packaged synchronous list/decide approval-domain shape. Produces a dashboard adapter and tab HTML, not an authenticated server or every possible App Home redesign. |
| Other Node interfaces, monoliths, Python, Java, .NET or Go | Engineering required | Extract/adapt trusted business logic or implement and review another recipe and independent verifier. Merely being a Slack application is insufficient. |
| Arbitrary App Home, forms, shortcuts and multi-step modals | No general shipped path | The successful two-step intake experiment is separate. Its extension recipe and fixture are not included in the stable ZIP. |
| Events, notifications and scheduled digests | Not ready in this release | No shipped recipe. The experimental notification target failed independent acceptance and its final repair did not compile. Repairs were stopped; it was not hosted in Teams. |
| APIs, databases and SaaS integrations | Integration-specific work | A compatible adapter may reuse an existing backend. Supply connectivity, secrets, permissions and safe cases for retries, throttling, lost confirmations and duplicate side effects. The reservation fixture is separate, not shipped. |
| Slack Workflow Builder / no-code exports | No shipped converter | Inspect triggers, connectors, approvals and data; select a reviewed Teams/Power Automate/vendor replacement or create a new recipe. |
| Vendor app without available backend source | Not source-convertible here | Evaluate its Teams offering, an approved integration or a separately designed replacement. Installed-app metadata does not grant access to vendor code. |
| Messages, channels, files, directory records or existing business data | Outside scope | This is application-code migration, not workspace, history, directory or database migration. Plan those transfers separately. |
| Provisioning, SSO, production rollout and operations | Outside scope | Supply tenant configuration, infrastructure, identity, durable state, consent, monitoring, rollback and production acceptance. |

"Defined path" means there is a generation and verification contract. It does
not guarantee first-attempt success, complete business equivalence, or that
unreviewed source is safe to execute.

### Exact source contracts

The bot workflow requires allowlisted `domain.mjs` and `slack.mjs`, an explicit
identity map and command/action acceptance scenarios. Its replay instantiates
`createService()`, registers `registerSlackHandlers(app, { service })`, invokes
the supported callbacks and compares the observable results and synchronous
`snapshot()` state. A Slack manifest or workspace export alone is not enough.

The Home workflow additionally requires synchronous `execute()` list/decide
operations and the documented request-version, requests/audit and actor shapes.
The generated `handleDashboard(service, actorId, input)` must use the trusted
server-supplied actor, not an identity or role supplied by the browser.

The five packaged fixtures are stock lookup, maintenance approval, policy
lookup, delivery exceptions and manager approvals. They are synthetic examples,
not customer applications or production data.

## Prerequisites and dependencies

### Local installation

- A reviewed copy of the **private** kit and permission to use its contents.
- Windows with PowerShell, Node.js **22+**, and npm. The preview's engine retains
  Windows command conventions; Linux/macOS are not accepted installation paths.
- Approved npm-registry/network/proxy access. Root installation uses the
  lockfile; the bot verifier separately prepares the pinned Teams SDK scaffold.
- An approved workstation or isolated runner. Source replay executes source
  code. File/path restrictions are not an OS sandbox for untrusted repositories.

### Paid investigation and generation

- A signed-in, approved GitHub Copilot CLI account with access to
  `gpt-5.4-mini`, appropriate entitlements and an approved credit allowance.
  This release does not silently escalate or fall back to another model.
- The original release was checked against CLI **1.0.86**; the current
  release-readiness exercise uses **1.0.89-3**. Required options include
  `--session-id`, `--usage-output-file`, `--max-ai-credits` and the scoped
  tool/path flags checked by `doctor`. A new CLI version must be checked.
- An inventory, authorised source-file allowlists, reviewed acceptance cases,
  identity mappings, app owners and scope/UX decisions.
- An operator to answer questions, inspect source-backed assessments and
  approve their exact hashes. These are named local labels, not authenticated
  business-owner or CI approvals.

`doctor` checks Node and CLI flag compatibility **without a model call**. Its
`ready: true` does not check sign-in, subscription entitlement, available
models, tenant access or production readiness. A live model invocation tests
only the account and model actually used at that time.

### Running the generated application

For a bot, supply appropriate Entra/bot and Teams registrations, tenant/admin
permission to install it, a reviewed manifest with actual IDs/icons/URLs,
HTTPS hosting, authenticated bot messaging, securely stored credentials and
real target-user mappings.

For a personal tab, additionally supply an authenticated HTTP host, TeamsJS
asset, tab configuration and session/list/decision endpoints. The generated
dashboard's integration contract is not a bundled server. A synthetic one-use
ticket mechanism is not production Entra SSO.

Supply independent UI and integration review as well. The extra Playwright
browser harness used in this release exercise is **not installed or run by the
packaged CLI**. The shipped Home verifier checks domain results/state/audit,
trusted-actor handling, syntax and static integration markers; it explicitly
reports `browserVerified: false`. An engineer must not treat that local pass as
proof that the frontend works.

For external services, supply authorised API/database connectivity, secrets,
permissions, retry/idempotency behaviour, safe test environments and durable
state. The kit does not discover credentials, move databases or establish
arbitrary live-backend equivalence.

Owner UAT, target-client/accessibility checks, load, retention, monitoring,
rollback and operational handover remain separate acceptance work.

## Safe installation and run sequence

Run these commands from the **private kit root**, not this documentation
repository:

```powershell
npm ci --ignore-scripts
npm test
npm --prefix .\portfolio test
npm --prefix .\portfolio run migrate -- doctor
```

These checks do not launch migration models. Regression tests use synthetic
fixtures and, for some controller scenarios, fake model responses.

Before using the example inventory, review its app list, source root and scope.
Its default `budgetCredits: 1000`, `invocationCredits: 75` and four attempts per
stage permit **new paid work**, not a free replay of previous migrations.
Choose your own approved allowance; native CLI caps are soft and in-flight work
can overshoot. Failed attempts remain chargeable and recorded.

```powershell
npm --prefix .\portfolio run migrate -- init examples\pilot.json
npm --prefix .\portfolio run migrate -- run ..\.portfolio-runs\three-app-pilot
npm --prefix .\portfolio run migrate -- status ..\.portfolio-runs\three-app-pilot
```

Use the reported questions and hashes for the answer/approval cycle. Do not
approve unseen plans. Inspect generated output and independent evidence before
recording local acceptance. A successful `run` process can simply mean it has
stopped at a question or approval barrier. Use `check STATE_DIR` to require
complete local verification and metering; that still does not mean deployed.

Use the npm command form: the Windows verifier needs npm's executable location.
Arguments after `npm --prefix` resolve from the `portfolio` directory.

## Exact artifact and evidence boundary

The 25 September 2026 release-readiness exercise uses a fresh extraction of
`slack-teams-portfolio-v0.2.0.zip`, separate from the development folder, with
this SHA-256:

```text
c9417110cd8a88f8e8e8747501683cb655d2ce4eb388deaaf1190a4f6c8f7f9d
```

The archive has 66 files: 65 manifest-listed files and its release manifest.
Its code is not the experimental extension code in the working repository.
Testing does not replace the archive, manually repair generated targets, or
turn it into a public release.

The exercise uses the existing Windows workstation and approved Copilot
account. It is **not** a clean-machine, different-user, Linux/macOS or
customer-tenant test. Source fixtures and acceptance data are synthetic.
Raw source, generated code, usage logs, local paths, identities and original
evidence remain private.

### Setup and deterministic results

On Node **24.14.0**, npm **11.9.0** and Copilot CLI **1.0.89-3**:

| Check | Result | What it does not prove |
| --- | --- | --- |
| Archive integrity | All 65 manifest-listed files matched their original bytes. | This does not turn the archive into a public release. |
| Fresh-folder dependency install | Passed with lifecycle scripts disabled. | Not a clean-machine, empty-cache or different-account install. |
| Packaged engine suite | 18 checks passed. | Synthetic fixtures, not customer acceptance. |
| Packaged portfolio suite | 19 checks passed. | Some controller checks use fake model responses; no real-model success is inferred from them. |
| `doctor` and sample intake | Flags passed; two jobs prepared with the dashboard's required scope-answer barrier. | `doctor` does not check authentication or model entitlement. |
| Blocked-source cases | Vendor-no-source, manual-review/different-stack and missing-source entries remained blocked; running and resuming made zero model calls. | No conversion of those unsupported inputs was attempted or claimed. |
| Completion and approval gates | Incomplete portfolio check rejected; stale assessment hash rejected before current-plan approval. | Reviewer labels are local synthetic-test labels, not customer sign-off. |

Before claiming independent-adopter readiness, complete a separate-user,
clean-machine pilot with a new authorised application and that user's own
tenant/integrations, resolve or explicitly reject failed targets, and make the
additional UI/integration review repeatable. Do not treat historical live
demonstrations, deterministic controller tests, new model generation and
production acceptance as equivalent.

### Fresh policy-generation failure

The new policy assessment passed review, but generation exhausted its four
implementation slots: one initial implementation and three repairs. The final
target had an SDK callback return-type error, using `"message"` where the pinned
SDK expected `"application/vnd.microsoft.activity.message"`. It also introduced
a card-action handler even though the policy source is a command-only lookup.

The SDK compiler rejected the target. It did not reach passing target callback
replay, local acceptance or deployment. The generated code was not manually
patched and the attempt limit was not extended. Its **30.120300 managed credits**
include assessment, initial implementation and all three failed repairs.

This result does not erase the earlier successful policy demonstration. It
shows that a fresh model run from an installable package can still fail, and
that passing installation/controller tests is not sufficient for an
"install it and everything works" claim.

### Fresh dashboard outcome and independent browser review

The new dashboard reached **local acceptance after two model repairs**. Its
unchanged domain passed 12 scenarios / 14 steps, including trusted-actor
spoofing checks. The separately supplied browser harness then checked:

- Filtering, decisions, exact business refusals and audit.
- Retention of the exact successful decision text after a list refresh.
- Removal of queue, audit, hidden detail text and entered rejection text on 401.
- Explicit rejection of malformed successful list payloads and malformed rows.
- Explicit errors for malformed successful decision payloads and malformed JSON.
- Retry from a locked shell using fresh Teams context.
- An expired session's late list response not restoring private data, with busy
  state cleared and the shell remaining locked.

The nine scenarios passed on the final revision. Desktop/mobile views were
also reviewed. The initial domain-level pass did not establish this: browser
review found four defects. The first repair corrected them but left a stuck
busy state after expiry; the second repair fixed that. Both rejections and
all repair costs remain recorded. The coordinating assistant did not manually
patch the generated targets.

This is a synthetic headless-browser/API-interception test using the generated
real domain and adapter. It is not a native Teams deployment, production SSO,
live customer backend or comprehensive production acceptance test.

The **whole two-asset portfolio remains incomplete** because the policy bot
failed. Its `check` command correctly exits nonzero. Resuming after dashboard
acceptance and policy-attempt exhaustion made zero new worker invocations.
The original archive and both source-domain copies remain unchanged.

## Final managed costs: assets and kit operations

The user approved a **new 200-credit allowance** for this release test. All
nine runner invocations used GPT-5.4 mini, with two resumed worker sessions.
Native usage/result evidence reconciled completely; costs below are
incremental, not sums of cumulative snapshots.

| Asset | Final outcome | Assessment | Initial implementation | Repairs | Total AI credits |
| --- | --- | ---: | ---: | ---: | ---: |
| Policy lookup | Verification failed; four attempts exhausted | 4.090995 | 16.338975 | 9.690330 | **30.120300** |
| Approvals dashboard | Accepted locally after two repairs | 6.569730 | 26.832720 | 22.534440 | **55.936890** |
| Total | One accepted, one failed; portfolio incomplete | **10.660725** | **43.171695** | **32.224770** | **86.057190** |

**113.942810 credits remained.** Failed attempts are not removed from the bill.
No paid `clarify` or `discuss` invocation occurred in this run; the recorded
scope answer was deterministic. Investigation through the two model
assessments is included.

| Cost scope | Treatment |
| --- | --- |
| Runner-managed assessment, clarification, consultation, generation and repairs | Metered per app/stage. This exercise's final managed sum is **86.057190 credits**. |
| Dependency installation, deterministic regression tests, intake, answer recording, approvals, compilation/replay, status, reporting, reconciliation and guarded resume | **0 additional migration-model credits** for these operations themselves. This does not price machine/CI time, network, licences or operator effort as free. An assistant operating or interpreting them can add separate AI usage. |
| Outside coordinating conversation, source/review assistance, browser harness/review and website/documentation work | **Unallocated, not zero.** No complete task-aligned native checkpoint pair is available for this conversation; a preceding cumulative checkpoint includes earlier work and cannot be assigned to these assets. No unsupported full-task or per-app allocation is invented. |
| Staff effort, external integrations, live deployment, ongoing hosting and licences | Separate organisational/infrastructure costs, not priced in AI credits here. No new tenant deployment or production host was provisioned in this test. |

Therefore **86.057190 is not the all-in cost of the exercise**. The private
ledger retains invocation stage, model/session, timestamps, usage/event hashes,
incremental credits, input/cache/output tokens and API-call counts. Token cache
counts are not added to input tokens again, and nested meters are not added
on top of session totals.

For future budgeting, route app/shared investigation through the kit's
`discuss` command when it should be metered, track external work separately,
and use representative pilots that include failed assets and repair effort.
Do not multiply a successful worker price by the portfolio size and call it a
complete programme estimate.

These migration costs are not a per-request charge for end users of the
demonstrated deterministic services. Existing AI or external-service
dependencies in a different application need their own operating-cost review.

The [earlier 198.358950-credit three-app batch](acceptance.md),
[252.508065-credit coverage batch](coverage.md), and
[historical worker measurements](migrations.md) are separate scopes and are
not silently added to this run.
