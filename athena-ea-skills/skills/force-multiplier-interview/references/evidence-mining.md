# Stage 3 — Evidence assembly

The EA's history with their AI agent is the primary evidence source. It is
the one thing that reliably exists at a cold start.

This guide is **agent-agnostic**. It describes what to find and how to treat
it. Use whatever history access your environment provides.

## Getting at the history

| Environment | Approach |
|---|---|
| Claude (claude.ai, Desktop, Cowork) | `conversation_search` by keyword, `recent_chats` to bound a period, `read_conversation` to open a hit |
| Agents with their own session store | Whatever search or transcript access exists |
| No history access at all | Ask the EA to export or paste their history, or skip mining and run interview-only |

**Projects and workspaces fragment history.** In environments where a search
is scoped to the current project, a single pass reaches only that project's
chats. Ask the EA where their work lives, then run the mining once per
container. Missing this is the most common way the count comes out wrong.

## What to search for

Search the vocabulary of EA work, not the vocabulary of impact. The EA never
wrote "force multiplier" in a working session — they wrote "reschedule the
Thursday call."

Scheduling · calendar · travel · flight · hotel · itinerary · vendor ·
invoice · contract · expense · inbox · email draft · follow-up · research ·
summary · deck · agenda · minutes · onboarding · offboarding · playbook ·
process · automation · workflow · escalation · client update · report

Add whatever the EA named in Branch A1. Their own words for their own work
are better search terms than this list.

## What to extract per session

- **What they were doing** — one line, their category not yours
- **Roughly when** — the session date is enough
- **Any figure that appears** — "I do this 3x a week", "took me 4 hours",
  "handled 60 of these". These are gold; the EA said them casually at the
  time and will not remember them now.
- **Anything notable** — a crisis, a process they invented, a decision they
  made alone, praise from the client

Read selectively. Search broadly, open only the hits that look substantive.
Do not page through every conversation.

## Assessing volume before you count

Before presenting any number, judge whether there's enough to count.

**Thin history looks like:** a handful of sessions, a period much shorter
than the review period, categories from the interview with no hits at all,
or an EA who says most of their work happens off-tool.

**When it's thin, say so plainly and skip the counts entirely.** Something
like: *"Your AI history only covers about two months and most of your work
doesn't run through it, so counting sessions wouldn't tell us anything
useful. We'll build this from the interview instead."*

Then run the rest of the interview unaided. Do not produce a reconciliation
table. Do not show partial counts "for reference." A number that invites a
question you can't answer is worse than no number.

**Never extrapolate from a partial period to a full one.** This is the
single most tempting error here and the one most likely to blow up in the
review room.

## What this evidence is and isn't

State this to the EA when you report back, and again under any
reconciliation table:

> This covers AI sessions only. Phone calls, in-person work, anything handled
> in another tool, and anything you did without an agent are invisible to it.
> It's a floor, not a total.

Say it in those words. An EA who walks into a review with a number they
can't characterize is worse off than one with no number.


## Ingesting what the history can't see

Offer this. Declining is fine; skipping the offer is not.

AI history covers one agent. An EA's work also lives in task trackers,
meeting transcripts, email, and shared docs — all of it exportable, and all
of it invisible to a conversation search. Folding it in is the difference
between "what my agent saw" and something close to a real total.

| Skill | Does |
|---|---|
| `fulcra-ingest` | Profiles an uploaded export, builds idempotent annotation mappings, ingests the records |
| `fulcra-computed-data-types` | Generates a parser that tags records by a chosen dimension — here, task category |

Worth asking about: task tracker exports (Linear, Asana, Notion), meeting
transcript exports (Otter, Fireflies, Granola), email exports, and anything
their client's workspace lets them download.

**This needs a Python environment** — Claude Desktop or Cowork, not a plain
chat interface. If they're in chat, say so and note it as something they can
do later rather than pretending it's available.

Ingested records land in the same schemas as mined ones, so counts combine
cleanly. Record in state which sources were ingested and through what date —
the reconciliation has to be able to say where a figure came from.

## Recording what you find

Write countable, repeatable work as tracked records; write one-off or
story-shaped work as narrative notes. See `fulcra-setup.md` for where.

**When unsure, write the narrative.** An uncounted story is recoverable. A
miscounted event silently corrupts the math the whole case rests on.

If the history is thin and you're skipping counts, still write the narrative
— the sessions you found are real material for the interview even when
there aren't enough to total.
