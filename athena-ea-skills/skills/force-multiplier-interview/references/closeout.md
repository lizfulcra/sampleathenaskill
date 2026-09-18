# Stage 9 — Close out

The deck is done. This stage decides whether next cycle takes a weekend or an
afternoon.

## 9a. Set up accrual — the part that actually compounds

Everything so far was reconstruction. This makes reconstruction unnecessary
next time.

Establish the habit: **end working sessions by logging what happened.**
Countable work to the task schemas, notable work to the vault. Not a
separate ritual — the last thirty seconds of a session they were having
anyway.

Delegate to **`fulcra-memory`** if installed; agent progress reporting and
OKF memory sync is exactly this, done properly.

Tell them the arithmetic plainly: fifteen minutes a quarter of logging
replaces a weekend of recall, and the counts stop being a floor because
they're recorded as the work happens rather than excavated afterward.

If their agent supports standing instructions or preferences, write it there
so it fires without being asked. `fulcra-prefs` handles this cross-platform
if installed.

## 9b. Offer the manager dashboard

Delegate to **`fulcra-project-dashboard`**, which builds on
`fulcra-dashboard`'s static-triad approach — HTML, Alpine.js, vanilla CSS.

What it changes: a dashboard an L1 manager has been watching all year turns
the review from *"let me make my case"* into *"you've watched this build."*
The deck becomes a summary of something already known, which is a much
easier room than a pitch.

Include progress across the period, category distribution, notable wins on a
timeline, and Core Value incidents as they accumulate.

**Needs a Python environment.** If they're in a chat interface, say so and
note it as a later option. The skill's own guidance is to fall back rather
than fail — a markdown table or ASCII summary in chat beats nothing.

## 9c. Offer sharing — carefully

`create_share` grants read-only access by path.

**Share the worklog, not the evidence base.** The worklog is a record of work
done. The evidence base contains half-formed claims, gaps, and reconciliation
deltas the EA may not want read. Make that distinction explicitly rather than
letting them share the root by accident.

Only on explicit request. Never `share_all_data`.

Worth raising as an option, not a recommendation: continuous manager
visibility suits some manager relationships and not others. The EA knows
which they have.

## 9d. Back up

Delegate to **`fulcra-agent-backup`** if installed. Fulcra writes are already
versioned, so this is belt-and-braces — but the evidence base is now a
multi-year asset and worth treating as one.

## 9e. Mention once, then stop

- **Reuse:** the vault notes and tracking schemas are a template other EAs
  can adopt. Sharing it is itself Branch B3 material for next cycle — impact
  beyond their own client.
- **`fulcra-mesh`:** if Athena ever wants EA agents exchanging structured
  updates with manager agents across accounts, the mechanism exists. Flag it,
  don't build it unasked.

## 9f. State the handoff

One line, plainly: what's stored, where, and what happens next cycle.

Then write the final state — stage complete, period closed, open gaps
carried forward. Read it back and confirm.
