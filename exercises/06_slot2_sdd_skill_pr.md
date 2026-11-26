# Exercise 06 — Skills and sub-agents

**When:** Thu 26 Nov 2026, 11:00–12:00 and Fri 27 Nov 2026, 09:35–10:15 (Rome). **Example:** synthetic Card–Krueger panel.

Write your answers in [`notes/skills_log.md`](../notes/skills_log.md).

## A. Run a Skill (Thu 11:00–11:25)

1. Read [`.claude/skills/replication-checker/SKILL.md`](../.claude/skills/replication-checker/SKILL.md). Note when to use it and what GREEN requires.
2. Run it:

   ```text
   Use the replication-checker Skill on examples/card-krueger-toy/.
   Do not edit any file. Report GREEN, YELLOW or RED, the exact command you ran,
   and its output. Do not claim a check passed unless you ran it.
   ```

3. Log the rating and the command.

## B. Create a Skill (Thu 11:25–11:55; finish overnight)

1. On a separate copy, copy [`templates/skill_template.md`](../templates/skill_template.md) to `.claude/skills/<your-skill>/SKILL.md` (Codex and Cursor: `.agents/skills/<your-skill>/SKILL.md`).
2. Fill in a name, one line on when to use it, and 3–6 numbered steps. Model: `.claude/skills/sample-restrictions-note/SKILL.md`.
3. Run it once on `examples/card-krueger-toy/`.
4. Fix one step that the agent misread. Log what you changed.

## C. What a sub-agent is (Fri 09:35–09:55)

Read [`.claude/agents/data-reviewer.md`](../.claude/agents/data-reviewer.md). Write down:

- its **job** (one line);
- its **limits** (the bounds set for this job);
- **what it hands back**.

A review is what this sub-agent hands back. Another sub-agent can hand back a cleaned file, the parallel-trends figure, or a pull request. A summary is one possible result, not the definition.

## D. Skill or sub-agent? (Fri 09:55–10:15)

Sort each task, then compare with a neighbour:

| # | Task | Skill or sub-agent? |
| --- | --- | --- |
| 1 | Recompute the DiD the same way after every data change | |
| 2 | Independently check my NJ/PA group coding | |
| 3 | Write the sample-restrictions note in the same format each time | |
| 4 | Check the literature claims in the README while I keep working | |
| 5 | Format the results table the same way for every draft | |
| 6 | Search the whole project folder for every mention of the sample restriction | |

Rule: use a Skill when the same steps should be reused in place. Use a sub-agent when the piece of work needs its own focus, its own files, or would crowd the main conversation.

## Done when

- [ ] One `replication-checker` rating with the command it ran.
- [ ] Your Skill file exists, ran once, and has one fix.
- [ ] Job, limits, and what `data-reviewer` hands back, written down.
- [ ] Six tasks sorted, with one reason you disagreed with your neighbour.

Reference: [`solutions/06_slot2_sdd_skill_pr_solution.md`](solutions/06_slot2_sdd_skill_pr_solution.md).
