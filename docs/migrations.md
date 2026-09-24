# Demonstrated migrations and evidence boundaries

All applications below were created as synthetic examples. No customer source,
production policies, business records or message history was migrated.
They demonstrate Copilot-assisted application adaptation, not universal
Slack-to-Teams conversion.

## 1. Maintenance approval bot

The source creates a maintenance request in Slack and supports authorised
approval/rejection. The Teams implementation uses native commands and Adaptive
Cards while preserving the original domain service.

The live demonstration exercised creation, approval, rejection, role refusals,
repeated decisions and conflicting decisions. Main and employee-role sequences
matched source business state and audit. Local replay covered eight scenarios
and 42 steps. The transport lessons became reusable checks: visible Slack card
text, non-replacing private Slack responses, Teams channel-feature registration,
and channel-root references for targeted native-command replies.

The corrected migration session consumed **327.52824 credits** using GPT-5.6 Sol.
That is one corrected run, not the total of every earlier prototype attempt.
It is also not the full coordinating, hosting or documentation cost.

## 2. Policy lookup bot

Slack private policy lookup became a native Teams command with private replies.
Approved versioned text was preserved. Unknown and retired topics were refused
instead of generating invented policy.

Three live operations per platform matched. Independent local replay covered
six scenarios and 18 transport-variant steps. The original `domain.mjs` remained
unchanged.

GPT-5.4 mini consumed **48.44712 credits**: source assessment 5.34297, initial
implementation 20.928015, repairs 22.176135.

## 3. Delivery-exception bot

Slack lookup and Escalate/Resolve buttons became a native Teams command and
private Adaptive Cards. Resolution before escalation was refused; an employee
could escalate but could not perform the coordinator-only resolution.
Repeated resolution was idempotent.

Five main-flow live operations per platform matched, with a separate employee
role phase. Independent local replay covered seven scenarios and 39
transport-variant steps. The original domain service remained unchanged.

GPT-5.4 mini consumed **28.59333 credits**: source assessment 5.278905, initial
implementation 15.90834, repairs 7.406085.

## 4. Manager App Home to Teams dashboard

The original Slack App Home was reviewed and operated before redesign.
Its stacked Block Kit queue and separate rejection modal became a Teams personal
tab with counters, search, filtering, selectable request details, an inline
rejection reason and audit history.

Approvals, rejection reasons, self-approval refusal and the senior-approver limit
continued to come from the unchanged domain. The actual Teams tab matched Slack
state and audit. Independent domain checks covered 12 scenarios and 14 steps,
including spoofed client identity. These checks are distinct from browser proof.

GPT-5.4 mini consumed **51.28941 credits**: assessment and assessment correction
9.192105, initial implementation 16.70445, implementation repair 25.392855.

## 5. HTTP-backed stock reservations

Six real Slack commands and six real Teams native commands produced identical
private results, three unique reservations, final stock and audit. Real HTTP
rate limits and loss of confirmation after commit required explicit same-key
retries; the adapter did not invent rollback or a replacement request key.
Independent concurrent SDK-callback checks also rejected overselling and
duplicate receipts. GPT-5.4 mini used **58.659000 managed credits**.

## 6. Shortcut and two-step service-desk intake

A real Slack global shortcut and details/review modal became a private Teams
launcher and native dialog. Explicit cancellation created no ticket; a
correctable validation failure remained editable. The submitted SD-1 ticket
and audit matched the source, with private confirmation in each client.
Teams X-close has no Slack-style `view_closed` callback; transient draft expiry,
not identical cleanup, is the documented limitation.
GPT-5.4 mini used **107.577315 managed credits**.

The same expansion attempted notifications/digests, but **did not complete that
migration**. Its live Slack source passed; additional target review rejected a
local pass, and the final approved repair failed compilation. The operator
stopped further repairs at **86.271750 managed credits**. It was not hosted in
Teams and has no successful Slack/Teams screenshot pair.

See `coverage.md` for the complete extension cost matrix, acceptance boundaries,
platform differences and failed-attempt history.

## What the cost numbers do and do not mean

The three earlier mini migration sessions total **128.32986 credits**. Those sessions
include their assessment, implementation and corrective resumes, counting only
the latest cumulative usage of each session.

They exclude coordinating investigation and conversation, building the original
Slack examples and harness, live configuration/testing, documentation, licences
and hosting. They are not full end-to-end migration prices. The maintenance and
mini workloads/scopes differ, so these numbers are not a controlled model
comparison or a valid per-app portfolio forecast.

The new portfolio runner is intended to fix this measurement boundary for
future work: all model activity launched through it is app/stage-scoped,
including investigation and consultation. Product development and conversations
outside it remain separately disclosed, not guessed or charged repeatedly to
every app.

## Evidence and production boundaries

The earlier private expanded walkthrough has nine original screenshots; that
earlier expanded screenshot set contains 22 hash-checked originals. It records native
Slack and Teams interactions, not a mocked preview. The public site deliberately
does not redistribute those unsanitised screenshots or tenant metadata.

The role checks used one real account with controlled alternate mappings, not
two-person privacy-isolation testing. Live hosting was temporary, state was
process-local, and dashboard access used an explicitly accepted demo-only bearer
handoff. No production SSO, durability, load testing, full accessibility audit,
mobile/desktop matrix, customer integrations or data transfer is established.

The v0.2 portfolio acceptance run is a **separate clean local generation test**.
Historical live deployment evidence does not automatically establish that a new
generated revision has been installed in a tenant.
