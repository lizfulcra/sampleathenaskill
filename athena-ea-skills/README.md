# Athena EA Skills

Agent skills for Executive Assistants at Athena, built on
[Fulcra Context](https://fulcradynamics.com) for durable evidence storage.

## Skills

### `force-multiplier-interview`

Runs an EA through the full Force Multiplier pipeline — the Athena
presentation of their achievements against the review rubric.

The problem it solves: EAs undersell themselves badly, because routine work
stops being visible while you're doing it, and because a year of it is
impossible to recall in one sitting. The pipeline attacks that from two
directions — a deliberately adversarial interview that refuses vague answers,
and a sweep of the EA's own AI work history for things they've forgotten.
Both are stored in the EA's Fulcra account, so the next cycle starts from
evidence instead of memory.

**Nine gated stages.** The deck is produced at Stage 8 and not before.

| # | Stage | Exit condition |
|---|---|---|
| 0 | Brief, consent & scope | Blockers cleared, consents given, period and work locations fixed |
| 1 | Inventory | Raw material on the table |
| 2 | Fulcra setup | Connection verified; workspace, vault, schemas live |
| 3 | Evidence assembly | History mined, exports ingested or declined, volume assessed |
| 4 | Interview | Every branch settled; each Core Value has an incident or a declared gap |
| 5 | Reconciliation | Every claim resolved to one sourced number |
| 6 | Synthesis | EA has read and corrected it |
| 7 | Pressure test | Two mock panel runs |
| 8 | Deck | Built, cut, stored |
| 9 | Close out | Accrual set up; dashboard and sharing offered |

**The deck presents achievements and contains no ask.** No salary figure, no
request, no negotiation.

#### What the agent must raise first

Stage 0 runs before any tool call. It covers two blockers (confirm the rubric
with the L1 manager; confidentiality obligations), three consents (reading
the EA's AI conversation history, creating a Fulcra account, the adversarial
interview style), and eight disclosures about limits.

#### Design rules worth knowing before you edit it

- **Never invent or extrapolate a number.** "40 sessions in two months, so
  call it 240" is the failure mode this pipeline exists to prevent.
- **Reconciliation is presented flat.** Estimate beside count, delta named,
  no verdict. The EA decides what it means.
- **Counts are never shown before the EA answers.** The gap between what they
  estimate and what the record shows is the most useful output, and revealing
  the number first destroys it.
- **Evidence is a floor, never a total.** Phone calls, in-person work, and
  anything done without an agent are invisible to it. The skill says so twice.
- **Health, location, and calendar data are excluded.** Including from the
  Wellness section, which is about working practice, not biometrics.

## Install

Clone into wherever your agent loads skills from:

```shell
git clone <this repo>
cp -r athena-ea-skills/skills/force-multiplier-interview <your skills dir>/
```

Typical locations: `~/.claude/skills/` for Claude Code, or the skills folder
your client exposes.

## Dependencies

None are hard requirements — the skill degrades and says so — but it
delegates to these where present rather than reimplementing them.

| Skill | Used for | Source |
|---|---|---|
| `fulcra-connect` | Device-code auth | [agent-skills](https://github.com/fulcradynamics/agent-skills) |
| `fulcra-workspaces` | Workspace, agent identity | agent-skills |
| `fulcra-vault` | Wikilinked OKF notes | [community-skills](https://github.com/fulcradynamics/community-skills) |
| `fulcra-tracking` | Annotation schemas | agent-skills |
| `fulcra-ingest` | Third-party export ingestion | agent-skills |
| `fulcra-computed-data-types` | Parsers tagging by task category | community-skills |
| `fulcra-analytics` | Auditable stats over records | agent-skills |
| `fulcra-memory` | Ongoing accrual | agent-skills |
| `fulcra-situational-awareness` | Resuming mid-pipeline | agent-skills |
| `fulcra-project-dashboard` | Manager-facing view | community-skills |
| `fulcra-agent-backup` | Evidence base backup | agent-skills |
| `grilling` (or similar) | Frontier-based interview rounds | optional |

## Environment

| Stage | Needs |
|---|---|
| 0, 1, 4, 6, 7, 8 | Any agent |
| 2 | Shell for CLI auth, **or** the Fulcra MCP connector |
| 3 (mining) | Conversation history search |
| 3 (ingestion), 5 (analytics), 9 (dashboard) | Python — Claude Desktop or Cowork |

In a plain chat interface the skill runs, tells the EA which stages are
reduced, and continues.

## Scope

Athena-specific. The rubric weights, the four Core Values, and the L1 manager
review flow are baked in throughout. Adapting it elsewhere means rewriting
`references/interview-branches.md` Sections C–E and the rubric table in
`SKILL.md`.

## Contributing

Corrections welcome, particularly to the rubric if Athena's criteria change.
The interview branches are the part most worth arguing about — Section C is
where most decks fail, and the demand for one specific incident per Core
Value is deliberately hard.

## License

MIT.
