# Additional application-pattern coverage

Recorded on 24 September 2026. All source applications and data were synthetic.
**Two migrations were accepted with separate live Slack/Teams proof. The third
failed acceptance and was stopped.** No notification success or universal
Slack-app compatibility is implied.

## Outcomes and managed cost

All workers used GPT-5.4 mini; there was no model escalation or coordinator
hand-edit of generated target code. These figures include unsuccessful worker
attempts, source assessment, clarification and repairs.

| Application | Assessment | Clarification | Initial implementation | Repairs | Total credits | Result |
| --- | ---: | ---: | ---: | ---: | ---: | --- |
| API reservations | 7.613115 | 3.269295 | 39.735840 | 8.040750 | 58.659000 | Accepted; live parity |
| Service-desk intake | 7.917465 | 0 | 44.903430 | 54.756420 | 107.577315 | Accepted; live parity |
| Notifications / digest | 11.283660 | 0 | 42.248505 | 32.739585 | 86.271750 | Failed; repairs stopped |
| Total | 26.814240 | 3.269295 | 126.887775 | 95.536755 | **252.508065** | Not a fully accepted batch |

The unchanged allowance was 1,000 managed credits; 747.491935 remained.
The two accepted apps total 166.236315 credits. This is separate from both the
earlier 198.358950-credit portfolio run and the historical worker demonstrations.
Native cumulative usage is reconciled incrementally, not added repeatedly.
Resuming after acceptance and exhaustion of the stopped job made zero new model
calls.

Coordinating conversation, source/recipe development, browser and HTTP harness
engineering, native deployment/testing and documentation are excluded. Their
full engineering cost is not established and is not represented as zero.
Human effort, hosting and licences are separate again.

## API reservations: an integration, not just a text bot

The source contract is asynchronous `execute`, with an injectable API and a
synchronous business snapshot. The existing command-bot recipe already awaits
callbacks; a new asynchronous recipe was unnecessary.

Each platform used its own fresh authenticated loopback HTTP backend with
identical synthetic stock. Six genuine native commands covered first receipt,
same-key duplicate, a real HTTP 429 and explicit retry, and loss of the response
after the backend had committed followed by another same-key retry.

Both ended with three unique receipts/audit entries, CHAIR stock 1 and LAMP
stock 1. Replies were private. The uncertain result explicitly said to reuse
the key; no rollback, new key or automatic successful confirmation was invented.
Local verification covered 7 scenarios and 42 transport steps. Additional
actual generated-callback checks used real HTTP and simultaneous duplicate or
competing-user calls. They confirmed a single reservation, not overselling.

This proves the reviewed synthetic integration, not an actual customer API,
durable inventory system, distributed concurrency design or production load.

## Service-desk intake: source review, redesigned native interaction

The Slack source uses a global shortcut, title/category details modal, review
step and private submission confirmation. The target uses native `/intake`,
a private Adaptive Card launcher, `dialog.open` and `dialog.submit`.

The preserved domain owns validation, draft ownership, five-minute expiry,
review-before-confirm, cancellation and duplicate-confirmation semantics.
Six local scenarios cover 32 transport steps. Native client checks then proved
explicit cancellation without creating a ticket, a correctable short-title
error remaining editable in the same draft, review, and private SD-1
confirmation. The final title, category, actor and audit match Slack exactly.

The generated target initially failed SDK compilation and later closed
correctable validation failures. Paid repairs corrected those before
acceptance. Explicit user extensions allowed seven implementation/repair
attempts in an eight-attempt allowance; the allowance was not silently raised.

There are real platform differences:

- Explicit Cancel bypasses required field validation and calls the service.
- Teams X-close does not supply Slack's `view_closed` callback. It creates no
  ticket, but transient draft access is denied after its semantic expiry rather
  than claiming identical immediate cache cleanup.
- This Teams client displays `task.message` inside the dialog until the user
  selects Close. The completed/cancelled form is no longer editable.

An initial Slack inspection draft expired while setup continued; closing it
created no ticket. An initial Teams test incorrectly expected result messages
to auto-close; the harness was corrected to observe native client behaviour.
Neither event is concealed or counted as a successful new business operation.

## Notifications and digest: useful failure evidence

The Slack source passed genuine bot mentions, private queue acknowledgements,
duplicate suppression, public alert delivery and a delayed digest. Two queue
items were sent once each. A malformed setup mention was explicitly refused
after inviting the bot to the approved channel and created no notification.

The target initially passed 5 local scenarios and 46 transport steps, including
known-rejection retries, retry bounds and ambiguous-delivery reconciliation.
Supplemental source/target callback checks then found a gap in that baseline:
unmapped identity and empty input were short-circuited by the adapter, which
invented refusal text instead of invoking the domain.

Independent review rejected that local pass. The final approved repair
corrected those branches but returned a business result from an SDK message
callback that must return `void`, causing TypeScript compilation to fail.
After six approved implementation/repair attempts, the operator declined
another extension. The job remains `verification_failed`, not accepted.
It was excluded from the Teams host and deployment overlay. No generated file
was manually patched to manufacture success.

The original 5-scenario baseline did not cover the two newly discovered edges.
The supplemental verifier and failure evidence remain in the private working
extension; the earlier baseline has not been rewritten after approval.
Future recipe acceptance should include these edges before another migration.

The notification queue is process-local demo state, not a durable outbox,
scheduler, crash-recovery implementation or exactly-once delivery guarantee.

## Narrow accounting recovery, not missing-usage forgiveness

One dialog repair failed before model execution when loading the model catalogue.
Its complete native cumulative usage matched the preceding invocation exactly,
with zero new requests/last-call tokens and startup-only events. The known
catalogue-timeout diagnostic, process result, timestamps and evidence hashes
were checked. It was recorded as a failed attempted invocation with measured
zero incremental credits and consumed an attempt slot.

This does not turn other missing result events or incomplete usage into zero.
Ambiguous accounting still blocks paid work.

## Reuse and release boundary

The extension supplies three source fixtures/jobs, a reviewed coverage inventory,
a narrow dialog recipe, an experimental notification recipe, source/target
callback comparison and explicit vendor-without-source disposition. The vendor
case stayed blocked without a model invocation. Verifier mutation fixtures are
test doubles, not migrated applications.

This public repository contains the website and case-study documentation,
including six genuine cropped Slack/Teams image pairs. **The toolkit source,
ZIP, source-app fixtures, experimental extension code and generated Teams
targets remain private.** This is documentation of an engineering approach,
not a product or toolkit-source release. Original captures and provenance are
preserved privately; public derivatives exclude tenant/account details through
explicit crops/redactions.

All acceptance is local synthetic-fixture review, not authenticated customer
owner sign-off. Live hosting is temporary; state is process-local. Service-token
and tenant validation remained enabled. No production SSO, durable storage,
customer data transfer, rollout or production acceptance was established.
The website and documentation are published separately from the private toolkit.
No MIT licence or toolkit-source distribution is part of this publication.
