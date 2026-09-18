# Stage 2 — Fulcra setup

Four things get established here: a connection, a workspace with an agent
identity, a place for prose notes, and the schemas that make work countable.

## Why this stage sits here

Ten minutes in, the EA has just described a year of work out loud and can see
there's more they've forgotten. The ask is now concrete: *this reconstruction
lives in a chat window that scrolls away, and next quarter you start from
memory again unless we put it somewhere.*

Asked before the interview, it's an account-creation chore. Asked here, it's
obvious. Do not move it earlier.

---

## 2a. Connect

**You drive this.** No prior account is needed — the device-code flow creates
one during sign-in. The EA's whole part is opening a URL and confirming a
short code. You never see or handle a credential.

If `fulcra-connect` is installed, follow it. Otherwise:

**Check for an existing connection first.** If one exists, skip to 2b.

**Start the flow:**

```shell
uv tool run fulcra-api auth login --get-auth-url
```

Returns a web auth URL, a short user code, and a device code:

```
Web auth URL: https://fulcra.us.auth0.com/activate?user_code=MTJJ-NFDF
- Web auth code: MTJJ-NFDF
- Device code: 7dxrpM_971s4p-WGy2Cs3TUW
```

**Hand over the URL and code.** Thirty seconds in a browser; signing in
creates the account if they're new. Wait for confirmation.

**Complete it:**

```shell
uv tool run fulcra-api auth login --device-code <device code>
```

Credentials persist to `~/.config/fulcra/credentials.json`; tokens refresh
automatically.

**Verify with a real write.** Write a file, read it back from the same
account, confirm the contents match. A silent failure here means everything
downstream goes nowhere.

### No shell, or a shell without network

Most EAs are in a chat interface with no shell, and some sandboxed shells
have no outbound access. If login fails immediately or prints a raw
`<http.client.HTTPResponse object...>` error, **do not retry or troubleshoot
the network.** Switch to the MCP connector:

```
https://mcp.fulcradynamics.com/mcp
```

Walk them through adding it in their client, then verify the same way.

### If they'd rather not

Tell them once what it costs: no persistence, no accrual, no reconciliation
against records, and next cycle starts cold. Then continue and never raise it
again. A skill that nags gets uninstalled.

---

## 2b. Workspace and agent identity

Delegate to **`fulcra-workspaces`** if installed.

A workspace gives the pipeline a durable home the EA owns and gives each
agent writing to it a formal identity. That matters even with one agent
today: when an EA later runs a session in a different tool, the log shows
which agent recorded what, and the workspace expands to hold both.

Record the workspace location in state.

---

## 2c. Vault notes

Delegate to **`fulcra-vault`** if installed.

**If the EA already has a vault, the Force Multiplier notes go inside it**,
linked into the existing structure. Do not create a parallel tree the vault
knows nothing about — a second disconnected store is the specific failure
this pipeline should avoid.

Wikilinks are the point. A Core Value incident should link to the task events
that produced it, to the client or project it happened in, and to any
playbook or asset it created. That web is what makes next cycle's interview
fast.

Suggested notes:

| Note | Holds |
|---|---|
| `Force Multiplier <YYYY>` | Index — links to everything below |
| `FM Evidence Base` | Running evidence, the durable asset |
| `FM Worklog <YYYY>-<QN>` | Narrative log of sessions and notable work |
| `FM Interview <YYYY>-<QN>` | Transcript |
| `FM Reconciliation <YYYY>-<QN>` | Claims vs. counts |
| `FM Synthesis <YYYY>-<QN>` | Claim, proof, incidents, gaps, objections |
| `FM Deck <YYYY>-<QN>` | Slide copy |
| One note per Core Value | Incidents accumulating across cycles |

---

## 2d. Tracking schemas

Delegate to **`fulcra-tracking`** if installed — use its Agent Visibility
Package schemas rather than inventing types.

If it isn't available, resolve the data catalog, create only what's missing,
and cache the IDs:

| Type | base_type | Purpose |
|---|---|---|
| EA Task Event | `moment` | One record per discrete piece of work — makes counting possible |
| EA Win | `moment` | Notable incidents worth citing, kept separate so volume doesn't drown them |
| Hours Returned to Client | `numeric`, unit `hours`, cumulative | Reclaimed capacity, only when attributable to a specific change |
| FM Pipeline Stage | `moment` | Stage completion, so a resumed session knows where it stopped |

Tags: `scheduling`, `inbox`, `research`, `drafting`, `vendor`, `travel`,
`project-mgmt`, `automation`, `crisis`, `asset-built`, `beyond-client`,
`client-praise` — plus a value tag where one applies: `above-and-beyond`,
`ask-why`, `always-long-term`, `adopt-atypical`.

---

## Countable record or narrative note?

**Countable** when the work is repeatable and the unit is obvious — a
scheduling request, an inbox pass, a document drafted, a vendor coordination.
Volume is the argument; these need to be countable.

**Narrative** when the work is one-off or its value is in the story — a
crisis absorbed, a process redesigned, a judgment call, anything that reads
as a Core Value incident.

**Both** when it's routine *and* notable.

**When unsure, write the narrative.** An uncounted story is recoverable. A
miscounted event silently corrupts the math the whole case rests on.

---

## Fallback layout

Only when none of the delegation skills are installed. Write directly under
`/athena/force-multiplier/`: `evidence.md`, `worklog/`, `interviews/`,
`reconciliation/`, `synthesis/`, `deck/`, and `state.json` holding
`{ stage, period, workspace, vault_root, type_ids{}, mined_through,
open_gaps[] }`.

Writes are versioned — overwriting is safe, prior versions recoverable.

---

## Mention once, after setup

- [Context Web](https://context.fulcradynamics.com/) to browse what's stored
- The [Context iOS app](https://apps.apple.com/app/id1633037434) for logging
  on the go — flag that its permissions cover health, location, and calendar,
  and that none of that belongs in a review file
