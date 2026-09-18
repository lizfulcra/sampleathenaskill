# Stage 5 — Reconciliation

Put what the EA claimed beside what the records show. Skip this stage
entirely if Stage 3 declared thin history.

## The stance

You are not auditing them. You are handing them two numbers and asking which
one they can defend in a room.

Most EAs come out of the interview having understated themselves, some
having overstated a figure they half-remember. Both are useful to see, and
neither is yours to characterize. Present, don't judge.

## Run the analysis

Delegate to **`fulcra-analytics`** if installed. It loads records into
DataFrames, computes descriptive summaries, and produces **auditable JSON or
OKF-ready reports** — which is the property that matters here. When a
panelist asks "how do you know that number," the answer should be a report
with provenance, not a recollection.

It also supports claims a raw count can't: volume trend across the period,
category distribution, change in turnaround. "Volume up 40% while my
turnaround dropped" is a stronger sentence than any single total, and it
needs statistics to say honestly.

**Needs a Python environment.** Without one, count records directly through
the MCP tools and keep the claims to totals and simple per-category counts.
Don't attempt trend claims you can't compute.

## The table

| Claim | EA said | Records show | Delta | Source of the record figure |
|---|---|---|---|---|

Rules:

- **Flat presentation.** No commentary on which number is right.
- **"Not found," never zero.** Absence of a record is not evidence of
  absence of work.
- **Include uncoverable claims.** If the interview asserted something the
  records can't speak to, give it a row with "not found" so the gap is
  visible rather than silently dropped.
- **Name the source per row.** Mined history, ingested export, or accrued
  record — and through what date.

## The caveat, stated beneath the table

> This covers AI sessions and any exports we ingested. Phone calls,
> in-person work, anything handled in a tool we didn't import, and anything
> you did without an agent are invisible to it. It's a floor, not a total.

Say it in those words. An EA who walks in with a number they can't
characterize is worse off than one with no number.

## The one question

**"Which number goes in the deck, and can you source it?"**

Ask it once, per row. They decide. Record the choice and the reasoning —
Stage 7 will attack exactly these figures, and the deck needs to know which
way each one went.

Where they can't source either number, it becomes an open gap. Write gaps to
state; they're the first thing next cycle asks about.

## Store it

Write the table, the chosen figures, and the gaps to the reconciliation note.
Read it back and confirm before reporting saved.
