---
name: force-multiplier-interview
license: "MIT"
user-invocable: true
description: "Run an Executive Assistant through the full Force Multiplier pipeline — the Athena presentation of their achievements against the review rubric. Nine gated stages: scope, inventory, Fulcra setup, evidence assembly from AI work history, deep interview against the rubric, reconciliation, synthesis, pressure test, deck. Evidence persists in the EA's own Fulcra account so each cycle compounds instead of starting from memory. Use when the user asks to prepare a Force Multiplier deck or presentation, present their achievements for review, run an impact interview, reconstruct what they did this quarter or year, log a win, resume a Force Multiplier in progress, or do a quarterly impact check-in. Also triggers on partial asks like 'help me prep for my Athena review', 'interview me about my impact', or 'what have I actually done this year'."
---

# Force Multiplier Pipeline

A Force Multiplier presentation fails for one of two reasons: the EA can't
remember what they did, or they can't prove it. This pipeline fixes both.

**The deck presents achievements. It contains no ask.** No salary figure, no
request, no negotiation. The EA shows what they did and what it produced;
Athena decides what follows. Any slide, sentence, or rehearsal question that
drifts toward asking for something is out of scope.

**The interview** produces claims. **Their AI work history and ingested
records** produce counts. **Fulcra** makes both survive past the chat window,
so next cycle starts from evidence instead of recall.

## This is a gated process

Nine stages. Each has an exit condition. **Do not produce the deck before
Stage 8**, and do not enter Stage 8 until Stages 0–7 have passed.

If the EA asks for the deck early — and they will — name the stage they're
at, name what's outstanding, and keep going. A deck built on an unfinished
interview is the thing this pipeline exists to prevent.

| # | Stage | Exit condition |
|---|---|---|
| 0 | Brief, consent & scope | Blockers cleared, consents given, period and work locations fixed |
| 1 | Inventory | Branch A1 complete — raw material on the table |
| 2 | Fulcra setup | Connection verified by write-and-read-back; workspace, vault, schemas live |
| 3 | Evidence assembly | History mined, exports ingested or declined, volume assessed |
| 4 | Interview | Branches A2–E settled; every value has an incident or a declared gap |
| 5 | Reconciliation | Every claim has one chosen, sourced number; gaps recorded |
| 6 | Synthesis | EA has read and corrected it |
| 7 | Pressure test | Two mock panel runs completed |
| 8 | Deck | Built, cut, stored |
| 9 | Close out | Accrual set up; dashboard and sharing offered |

Track stage completion in Fulcra from Stage 2 onward. A resumed session reads
it and picks up where it stopped — never re-asks a settled branch.

## Hard rules

- **Brief the EA before any tool call.** `references/before-you-start.md` runs
  first — before searching their history, before touching Fulcra, before the
  first question. It covers blockers, consents, and limits, and two of its
  items are genuine consent gates.
- **Never invent a number.** No source, no claim. Log it as an open gap.
- **Never extrapolate.** "40 sessions in two months, so call it 240" is a
  fabricated figure and exactly what a panelist will pull on. Count what
  exists. Label it a floor. Stop.
- **Never editorialize the reconciliation.** Estimate and count side by side,
  delta named, no verdict. The EA decides what it means.
- **Preserve stated uncertainty.** Do not promote an inference to a verified
  fact, in the interview or in anything written to Fulcra.
- **Verify every write.** Read it back from the same account and confirm the
  contents match before reporting it saved.
- **Drive the Fulcra setup yourself.** Device-code auth means you run the
  commands; the EA's part is one browser step, signup included if they're new.
- **Health, location, and calendar data are out of scope.** If their Fulcra
  account holds sleep, workout, or location records, do not read, reference,
  or offer them. None of it belongs in a review file — including in the
  Wellness section, which is about working practice, not biometrics.
- **Client confidentiality.** Accept anonymization without pressing. Never
  write client names, financials, or internal documents anywhere unless the
  EA puts them there.
- **Do not flatter.** Agreeable interviewing produces a weak deck.

## The rubric

| Weight | Criterion |
|---|---|
| **Performance (100%)** | Mastery of role · delivery beyond expectations · alignment with Athena Core Values |
| **Wellness & Development (10%)** | Learning · healthy work-life balance |
| **Advocacy & Impact (10%)** | Community or personal advocacy |

Core Values: **Above and beyond** · **Ask why** · **Always long term** ·
**Adopt atypical**.

## Assume a cold start

No Fulcra account. No stored data. No prior run. The one thing that reliably
exists is the EA's history with their AI agent. Everything else is built
during the pipeline.

---

## Stage 0 — Brief, consent & scope

**0a. Brief them.** Load `references/before-you-start.md` and run it before
any tool call. Blockers first (L1 rubric confirmation, confidentiality), then
consents (reading their AI history, creating a Fulcra account, the
adversarial interview style), then the limits they need to know going in.

**0b. Scope the run.** Establish the period being covered and **where their
AI work lives** — which projects, workspaces, tools, or agents. Stage 3
depends on this, and a wrong answer here silently halves the evidence.

*Exit:* blockers resolved or acknowledged, consents recorded, period fixed,
work locations listed.

## Stage 1 — Inventory

Run **Branch A1** from `references/interview-branches.md`. Nothing is asked
of them technically yet — this is ten minutes of talking about their own job.

*Exit:* A1 complete.

## Stage 2 — Fulcra setup

Load `references/fulcra-setup.md` and run it. Placed here deliberately:
they've just described a year of work and can see how much they'd forgotten,
so the ask is concrete rather than hypothetical.

Sets up connection, workspace with agent identity, vault notes, and tracking
schemas.

*Exit:* a write verified by read-back; workspace, vault location, and schemas
recorded in state.

## Stage 3 — Evidence assembly

Load `references/evidence-mining.md`.

Mine the AI work history across every location named in Stage 0. Then offer
export ingestion for everything the history can't see — task tools, meeting
transcripts, email. Ingestion is optional; declining is fine, but it must be
offered, because it's the difference between "what my agent saw" and
something close to the real total.

Assess volume before counting anything. Thin history means saying so plainly
and skipping counts entirely — a partial number invites a question that can't
be answered.

*Exit:* worklog written, volume assessed, counts produced or thin-history
declared.

## Stage 4 — Interview

Resume `references/interview-branches.md` at A2 and work through Section E.

**Seed questions with what Stage 3 found, but never show a count before they
answer.** The gap between estimate and record is the most useful output here,
and revealing the number first destroys it.

Checkpoint to Fulcra every few branches.

*Exit:* every branch settled; each Core Value has a specific incident or a
declared gap.

## Stage 5 — Reconciliation

Load `references/reconciliation.md`. Skip only if Stage 3 declared thin
history.

*Exit:* every claim resolved to one chosen number the EA can source; open
gaps written to state.

## Stage 6 — Synthesis

Load `references/deck-build.md`, section 1. Produce the synthesis and have
the EA correct it. They know their work better than the transcript does.

*Exit:* EA has read and corrected it.

## Stage 7 — Pressure test

`references/deck-build.md`, section 5. Two mock panel runs. The second is
measurably better than the first, which is why there are two.

*Exit:* both runs done.

## Stage 8 — Deck

`references/deck-build.md`, sections 2–4. Build, cut the weakest slide,
store.

*Exit:* deck stored in Fulcra and delivered in the format they chose.

## Stage 9 — Close out

Load `references/closeout.md`. Accrual habit, manager dashboard, sharing,
backup.

*Exit:* accrual set up; dashboard and sharing offered once.

---

## Resuming

At the start of any session, check Fulcra for an in-progress pipeline. If one
exists, open with a short recap — stage reached, what's settled, what gaps
are outstanding — and resume there. Delegate to
`fulcra-situational-awareness` if installed.

## If Fulcra genuinely can't be reached

Not "the EA would rather not" — that's handled in
`references/fulcra-setup.md`. This is no shell, no MCP connector, no path at
all. Then run Stages 0, 1, 3 (history only), 4, 6, 7, 8 in-session and tell
them once, plainly, that nothing persists and next cycle starts cold.
