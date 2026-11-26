# Demo — Using sub-agents, Orchestrating, Issue-board swarm (launch)

**When:** Fri 27 Nov 2026, 10:15–12:00 (Rome).
**Example:** the synthetic Card–Krueger panel.

## Using sub-agents (10:15–10:50)

**Say:** name the sub-agent and the bounds for this piece of work. It works in its own conversation and hands back what the job needs. These two reviewers may only read, and a review is what they hand back. You decide what to keep. Think of two research assistants: one reviews the cleaning, one checks the citations, and neither sees the other's notes.

**Reviewer 1:**

```text
Use the data-reviewer sub-agent on examples/card-krueger-toy/.
Read only. Report panel balance, missing values and NJ/PA coding problems,
most serious first.
```

**Reviewer 2:**

```text
Use the literature-reviewer sub-agent on examples/card-krueger-toy/README.md,
examples/card-krueger-toy/faults/citation_mismatch.md and
references/bibliography.bib. Read only. Flag any claim the sources do not support.
```

Expected: reviewer 2 flags that the toy DiD is cited as if it were Card and Krueger (1994).

**Say:** you decide. Log one finding you accept and one you reject in [`notes/orchestration_log.md`](../notes/orchestration_log.md).

**Codex / Cursor:** see [`tool-lanes/`](../tool-lanes/) for how each tool calls a helper. If none starts, paste the helper's file into a fresh chat and say so in the log.

## Orchestrating sub-agents and swarms (10:50–11:15)

**Say:** split the job, give each part to a different agent, put the results back together. A swarm is many agents at once; a human makes the final call. A PI with several RAs, each with their own files.

Show the writer and checker pair in [`examples/card-krueger-swarm/README.md`](../examples/card-krueger-swarm/README.md): the writer documents the panel, the checker reviews the literature claims, and they never edit the same file.

Participants split "replicate and extend Card–Krueger" into three jobs with no shared files.

## 11:15–11:25 Pause

Anyone planning a cloud agent fills [`agent-harness/autonomous_agent_risk_card.md`](../agent-harness/autonomous_agent_risk_card.md) now.

## Issue-board swarm: launch (11:25–12:00)

**Say:** each job is an issue, a to-do card on GitHub. Agents pick up cards marked `ready`, work in their own separate copy, and return a pull request linked to the card.

1. On GitHub, open two issues by pasting [`ck-data-cleaning.md`](../examples/card-krueger-swarm/issues/ck-data-cleaning.md) and [`ck-parallel-trends-figure.md`](../examples/card-krueger-swarm/issues/ck-parallel-trends-figure.md). Label both `ready`.
2. Start one agent per card. Cloud: Claude Code on the web, Codex cloud, or Cursor cloud agents, each pointed at its issue. Local: two windows, each on its own separate copy (most tools have a "worktree" or "parallel agent" option that makes the copy for you).
3. Prompt for each:

```text
Work on GitHub issue #<N> only. Change only the files it allows.
Run the check command it names. Open a pull request linked to the issue.
Do not edit tests or data files.
```

4. Move both cards to `in-progress`. Go to lunch.

**Rules:** no more than 2 cards live. No confidential data on a lunchtime run. Card flow and labels: [`docs/issues_tracking.md`](../docs/issues_tracking.md).
