# Reference — Exercise 06

## A. replication-checker

Expected: the agent runs

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

sees all checks pass, and reports **GREEN** (or **YELLOW** if it flags something it could not check, such as a fresh install). A rating without a command and its output does not count.

## B. Your Skill

A good Skill file is short:

```text
---
name: sample-restrictions-note
description: Use when writing or checking the sample-restriction note for a panel.
---
1. Run python3 examples/card-krueger-toy/src/panel_workflow.py.
2. List every rule that drops rows, in order.
3. Give the row count after each rule.
4. Quote the command you ran.
5. Do not edit data or code.
```

Expected counts for the Card–Krueger panel: 47 raw rows → 43 after the status filter → 42 after dropping missing values → 36 rows (18 stores) in the balanced panel.

Typical fix after the first run: the agent paraphrased the counts instead of quoting them, so add "copy the counts exactly as printed".

## C. data-reviewer

- **Job:** review documentation, panel balance, missing values and NJ/PA coding.
- **Limits:** this job may read and search; it cannot edit files or run commands. That bound is the job, not the definition of a sub-agent.
- **What it hands back:** a review (a list of findings). A cleaned file, the parallel-trends figure, or a pull request is another possible result. A summary is one possible result, not the definition.

## D. Skill or sub-agent

| # | Answer | Why |
| --- | --- | --- |
| 1 | Skill | Same steps, reused in place |
| 2 | Sub-agent | Needs its own focus: it should not share your reasoning |
| 3 | Skill | Same steps, reused in place |
| 4 | Sub-agent | Own focus; it would crowd the main conversation |
| 5 | Skill | Same steps, reused in place |
| 6 | Sub-agent | Own focus; the search would crowd the main conversation. It hands back the list of mentions |

Reasonable disagreement: task 2 could be a Skill if you always check coding the same way, in this conversation. It is a sub-agent when it needs its own focus and must not see your reasoning.
