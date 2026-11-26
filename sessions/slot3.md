# Slot 3 — Fri 27 Nov 2026, 10:15–12:00 (Rome)

Using sub-agents, running several agents at once, and an issue-board swarm that works over lunch.

| Clock | Block | You do | You write |
| ---: | --- | --- | --- |
| 10:15–10:50 | Using sub-agents | Run two reviewers, compare their reports | `notes/orchestration_log.md` |
| 10:50–11:15 | Orchestrating sub-agents and swarms | Split one job into three that share no files | `notes/orchestration_log.md` |
| 11:15–11:25 | Pause | Fill the risk card if you will use a cloud agent | `agent-harness/autonomous_agent_risk_card.md` |
| 11:25–12:00 | Issue-board swarm | Open two cards, start two agents | two issues, two agents running |
| *12:00–14:00* | *Lunch* | *The agents work; you don't* | |

## Using sub-agents (10:15–10:50)

Name the sub-agent and the bounds for this piece of work. It works in its own conversation and hands back what the job needs. These two reviewers may only read, and a review is what they hand back. You decide what to keep. Think of two research assistants: one reviews the cleaning, one checks the citations, and neither sees the other's notes.

Run [`data-reviewer`](../.claude/agents/data-reviewer.md) and [`literature-reviewer`](../.claude/agents/literature-reviewer.md) on the Card–Krueger folder. Exercise: [`07_slot3_subagents_vc.md`](../exercises/07_slot3_subagents_vc.md), part A.

## Orchestrating sub-agents and swarms (10:50–11:15)

**Orchestrating** means splitting a job into parts, handing each part to a different agent, and putting the results back together. A **swarm** is many agents working at the same time. A human still makes the final call, like a PI running several RAs, each with their own files.

Rule: two agents must never edit the same file. See the writer and checker pair in [`examples/card-krueger-swarm/README.md`](../examples/card-krueger-swarm/README.md). Exercise: part B.

## Issue-board swarm: launch (11:25–12:00)

Each job is written as an **issue**, a to-do card on GitHub. Agents pick up cards marked `ready`, work in their own separate copy, and send back a pull request linked to the card. Cards move `ready` → `in-progress` → `needs-review` → `done`, like a job board where whoever is free takes the next card.

Two cards only: [`ck-data-cleaning`](../examples/card-krueger-swarm/issues/ck-data-cleaning.md) and [`ck-parallel-trends-figure`](../examples/card-krueger-swarm/issues/ck-parallel-trends-figure.md). Card flow: [`docs/issues_tracking.md`](../docs/issues_tracking.md). Exercise: part C.

**Before any cloud agent**, fill [`agent-harness/autonomous_agent_risk_card.md`](../agent-harness/autonomous_agent_risk_card.md). No confidential data on a lunchtime run. If cloud agents are not available, use two local windows, each on its own separate copy.

## Leave for lunch with

- Two reviewer reports, with one finding accepted and one rejected in the log.
- A three-way split of "replicate and extend Card–Krueger" with no shared files.
- Two cards labelled `in-progress` and two agents working.

Review happens at 14:00 ([`slot4.md`](slot4.md)). Reference answers: [`exercises/solutions/07_slot3_subagents_vc_solution.md`](../exercises/solutions/07_slot3_subagents_vc_solution.md).
