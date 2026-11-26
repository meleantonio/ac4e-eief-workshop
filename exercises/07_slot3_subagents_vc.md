# Exercise 07 — Using sub-agents, Orchestrating, Swarm launch

**When:** Fri 27 Nov 2026, 10:15–12:00 (Rome). **Example:** synthetic Card–Krueger panel.

Write your answers in [`notes/orchestration_log.md`](../notes/orchestration_log.md).

## A. Two reviewers (10:15–10:50)

These two are bounded to a review. A review is one result a sub-agent can hand back. A cleaned file or the parallel-trends figure is another.

1. Run both reviewers. For this job, read only:

   ```text
   Use the data-reviewer sub-agent on examples/card-krueger-toy/.
   Read only. Report panel balance, missing values and NJ/PA coding problems.
   ```

   ```text
   Use the literature-reviewer sub-agent on examples/card-krueger-toy/README.md,
   examples/card-krueger-toy/faults/citation_mismatch.md and
   references/bibliography.bib. Read only. Flag claims the sources do not support.
   ```

2. Log one finding you **accept** and one you **reject**, with a reason each.

## B. Split the job (10:50–11:15)

Split "replicate and extend Card–Krueger" into **three jobs that share no files**. For each, write: the job in one line, the files it may change, and who reviews it.

## C. Launch two cards (11:25–12:00)

1. Fill [`agent-harness/autonomous_agent_risk_card.md`](../agent-harness/autonomous_agent_risk_card.md) if you will use a cloud agent.
2. On GitHub, open two issues from [`ck-data-cleaning.md`](../examples/card-krueger-swarm/issues/ck-data-cleaning.md) and [`ck-parallel-trends-figure.md`](../examples/card-krueger-swarm/issues/ck-parallel-trends-figure.md). Label them `ready`.
3. Start one agent per card (cloud, or two local windows each on its own separate copy):

   ```text
   Work on GitHub issue #<N> only. Change only the files it allows.
   Run the check command it names. Open a pull request linked to the issue.
   Do not edit tests or data files.
   ```

4. Relabel both cards `in-progress` and go to lunch.

No more than 2 cards. No confidential data.

## Done when

- [ ] One accepted and one rejected finding, each with a reason.
- [ ] Three jobs with no file in common.
- [ ] Two cards `in-progress`, two agents running.

Reference: [`solutions/07_slot3_subagents_vc_solution.md`](solutions/07_slot3_subagents_vc_solution.md).
