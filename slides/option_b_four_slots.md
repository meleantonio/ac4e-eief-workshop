---
marp: true
theme: default
title: Agentic Coding for Economists: EIEF / Luiss
description: Fourteen ideas, one example (Marp mirror of the 57-frame Beamer projector)
paginate: true
style: |
  section {
    font-size: 28px;
    padding: 42px 52px;
  }
  h1, h2 {
    color: #005b96;
  }
  code {
    color: #009688;
    background: #f5f5fa;
    padding: 0.05em 0.25em;
  }
  table {
    font-size: 0.82em;
  }
  blockquote {
    border-left: 6px solid #005b96;
    background: #f5f5fa;
    padding: 0.55em 0.85em;
  }
---

# Agentic Coding for Economists
## EIEF / Luiss: eight hours, fourteen ideas

Thu 26 Nov 2026, 09:00–12:00 · Fri 27 Nov 2026, 09:30–12:00 and 14:00–16:30 (Rome)

Antonio Mele · Claude Code, Codex, and Cursor

One example all day: the synthetic Card–Krueger panel

Paste this into Claude Code, Codex, or Cursor.

```text
Go to https://ac4e-eief-workshop.vercel.app/ and follow instructions.
```

Beamer projector: `slides/workshop/workshop_slides.pdf`

---

# Fourteen ideas on the Rome clock

| Slot | Clock (Rome) | Ideas |
| --- | --- | --- |
| 1 | Thu 09:00–11:00 | Agent vs chatbot · Version control · `AGENTS.md`: boundaries first · To-do lists |
| 2 | Thu 11:00–12:00 + Fri 09:30–10:15 | Skills: why · Create a Skill · Sub-agent vs Skill · Skill or sub-agent? |
| 3 | Fri 10:15–12:00 | Using sub-agents · Orchestrating and swarms · Issue-board swarm (agents work over lunch) |
| 4 | Fri 14:00–16:30 | Goals · Acceptance criteria · Verification · Capstone · 7-day plan |

Each idea: definition, everyday comparison, Card–Krueger example, your turn.

---

# One example all day: Card–Krueger

- April 1992: New Jersey raises its minimum wage; Pennsylvania does not.
- Compare fast-food jobs before and after: the NJ–PA difference-in-differences.
- Our folder: `examples/card-krueger-toy/`.
- **Synthetic teaching data**, not the real survey. No research claims.

The check command we run all day:

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

---

# Room rules

*[09:00–09:10]*

- You are the manager; the agent is a fast RA.
- Every agent change is a **proposal** until you read it and the check passes.
- Agents never certify identification or causality. That is your job.
- No confidential data, referee files or passwords in any prompt.

First, check your laptop:

```bash
python3 scripts/validate_setup.py
```

---

# Slot 1 · Thu 09:00–11:00

| Clock | Block |
| --- | --- |
| 09:00–09:10 | Welcome, room rules, laptop check |
| 09:10–09:30 | Agent vs chatbot |
| 09:30–09:55 | Version control: your first pull request |
| 09:55–10:35 | `AGENTS.md`: boundaries first, with privacy |
| 10:35–10:45 | Pause / set-up help |
| 10:45–11:00 | To-do lists |

---

# Agent vs chatbot

*[09:10–09:30]*

> **In plain words:** A chatbot only talks. An agent can also act: it opens your files, runs your code, reads the result and tries again.

**Think of it as:** phoning a friend for advice vs hiring an RA who sits at your desk.

---

# Card–Krueger: same question, two answers

**"What is the NJ–PA change in employment?"**

| Chatbot | Agent |
| --- | --- |
| Guesses a number from what it remembers about the 1994 paper. | Runs `did_analysis.py` on our folder and quotes the printed note. |

Only one of these answers comes from **your** data.

---

# Your turn

*Your turn · read only, nothing is edited*

1. Ask a plain chat: "What is the NJ–PA change in employment?"
2. Ask the agent the same question, adding "Do not edit any file."
3. Compare: where did each number come from?

Guide: `demos/slot1_workflows.md` · `exercises/04_slot1_workflows.md`

---

# Version control

*[09:30–09:55]*

> **In plain words:** A record of every saved version of the project, each with a note, so you can see what changed and go back. GitHub keeps that record online and lets others review changes before they are accepted.

**Think of it as:** Track Changes plus dated "save as" copies, shared with coauthors.

---

# GitHub Flow: copy, review, merge

The straight line is the main version. The picture still calls it `master`. Your change takes the lower path, then comes back.

![GitHub Flow diagram. The master branch is a straight line. A lower path creates a branch, commits changes, opens a pull request, gets feedback, tests, and merges back.](workshop/figures/github-flow.png)

**create branch** = separate copy · **commit changes** = saved version  
**Pull Request** and **get feedback** = the review · **test changes** = run the check  
**merge branch** = joins the main line

---

# Card–Krueger: reading the agent's edit

- The agent edits `examples/card-krueger-toy/README.md`.
- GitHub shows a list of changes: green lines added, red lines removed.
- You accept, or ask for a fix, before it joins the main version.
- Nothing is lost: every saved version can come back.

---

# Your turn: first pull request

*Your turn · 09:30–09:55*

1. Make a separate copy.
2. Edit one line in `notes/lane_choice.md`: your tool and why.
3. Save the version with a short note.
4. Open a pull request and read its list of changes.
5. Review, then merge.

Guide: `sessions/slot1.md` · `exercises/05_slot1_governance.md`

---

# `AGENTS.md`: boundaries first

*[09:55–10:35]*

> **In plain words:** A plain-text rules file the agent reads before it starts any task. It says what the agent may touch, what it must never do, and how to check its work.

**Think of it as:** the house rules you give a new RA on day one.

---

# Card–Krueger: the agent refuses

Two lines from our `AGENTS.md`:

```text
- Do not modify raw data.
- Do not let agents certify identification, causality, or interpretation.
```

Demo: ask the agent to edit `toy_fast_food.csv`.  
Watch it refuse and point to the rule.

---

# Privacy in three questions

1. How sensitive is the data?
2. Who may see it?
3. Where does the agent run: your laptop or someone else's computer?

> **Faculty default:** Anonymize · authorize · keep it on the machine

Full check: `docs/privacy_boundary.md`

---

# Your turn

*Your turn · 09:55–10:35*

1. Read `AGENTS.md` (two minutes).
2. Add one rule you would want for your own project.
3. Fill in the privacy check in `docs/privacy_boundary.md`.

Guide: `demos/slot1_governance.md` · Pause 10:35–10:45

---

# To-do lists

*[10:45–11:00]*

> **In plain words:** Before acting, the agent writes the steps it plans to take as a checklist. You edit the list, then it works through it and ticks items off.

**Think of it as:** a shopping list you check before anyone drives to the store.

---

# Card–Krueger: plan only

`Plan only, do not edit. Task: examples/card-krueger-goals/goals/ck-robustness-checks.md`

- [ ] Load the panel
- [ ] Check that every store appears before and after
- [ ] Compute NJ and PA group means
- [ ] Drop one store at a time and recompute
- [ ] Write a short note

---

# Your turn

*Your turn · 10:45–11:00*

1. Ask for the to-do list only.
2. Delete or reorder one step.
3. Let the agent do step 1 only, then stop.
4. Paste the list in `notes/modes_playbook.md`.

Template: `templates/agent_task_contract.md`

---

# Slot 2 · Thu 11:00–12:00 + Fri 09:30–10:15

| Clock | Block |
| --- | --- |
| Thu 11:00–11:25 | Skills: why |
| 11:25–11:55 | Create a Skill |
| 11:55–12:00 | Thursday wrap, overnight task |
| Fri 09:30–09:35 | Recap |
| 09:35–09:55 | Sub-agent vs Skill |
| 09:55–10:15 | Rule of thumb: Skill or sub-agent? |

---

# Skills: why

*[Thu 11:00–11:25]*

> **In plain words:** A Skill is a saved set of instructions for a task you do often. The agent follows it the same way every time, and you can share it with coauthors.

**Think of it as:** a recipe card, in place of explaining the dish from memory each time.

---

# Card–Krueger: `replication-checker`

Does our folder reproduce its numbers from a fresh start?

- File: `.claude/skills/replication-checker/SKILL.md`
- Inside: a name, when to use it, numbered steps.
- It runs the check command and confirms the data file is unchanged.
- It reports **GREEN**, **YELLOW** or **RED**, with the output as evidence.
- It never certifies causality.

---

# Your turn

*Your turn · Thu 11:00–11:25*

1. Read the Skill file before you trust it: what may it run?
2. Run it on `examples/card-krueger-toy/`.
3. Write down its colour and the one line of evidence behind it.

Guide: `demos/slot2_sdd_skill_pr.md` · `exercises/06_slot2_sdd_skill_pr.md`

---

# Create a Skill

*[Thu 11:25–11:55]*

> **In plain words:** Make a folder and write a short file in it with a name, a line saying when to use it, and numbered steps. Test it once and fix whatever was unclear.

**Think of it as:** writing down your referee-report checklist so a student can follow it.

---

# Card–Krueger: `sample-restrictions-note`

`.claude/skills/sample-restrictions-note/SKILL.md` (shape of the file)

```markdown
---
name: sample-restrictions-note
description: Use after any change to the Card-Krueger sample.
---
1. List every rule that drops stores.
2. Give the store count after each step.
3. Quote the command that printed the counts (panel_workflow.py).
4. Never edit the data file.
```

The header lines between the dashes: its name and when to use it.

---

# Your turn

*Your turn · Thu 11:25–11:55*

1. Fill in `templates/skill_template.md`.
2. On your separate copy, save it as `.claude/skills/<name>/SKILL.md`.
3. Run it once on the Card–Krueger folder.
4. Fix the one step the agent misread.

---

# Thursday wrap and Friday recap

*[Thu 11:55–12:00 · Fri 09:30–09:35]*

> **Tonight:** Draft one Skill for a task you repeat every week (`docs/between_sessions.md`).

> **Friday 09:30: so far:** Agent · saved versions · rules file · to-do list · Skills

---

# Sub-agent: what it is

*[Fri 09:35–09:55]*

> **In plain words:** A sub-agent is another agent you hand a piece of the work. It has its own conversation and its own instructions. Inside the bounds you set, it can read, write, check, and decide. It hands back whatever that job needs: a cleaned file, a figure, a review, a pull request, or a short report. A summary is one possible result, not the definition. A Skill is a repeatable set of instructions followed in the same conversation. A sub-agent carries out the piece of work on its own, in a fresh context.

**Think of it as:** a research assistant who redoes the Card–Krueger sample, rebuilds the parallel-trends figure, or reviews the cleaning, and hands the result back.

---

# Card–Krueger: Skill vs sub-agent

|  | Skill | Sub-agent |
| --- | --- | --- |
| What it is | Repeatable instructions, in this conversation | Another agent, with its own instructions |
| Where | Same conversation | Its own conversation (a fresh context) |
| Hands back | The steps, done in place | A file, a figure, a review, a pull request, or a short report |
| Example | `replication-checker` | `data-reviewer`, or the parallel-trends figure |

Inside the bounds you set, it can read, write, check, and decide. A summary is one possible result, not the definition. `data-reviewer` is bounded to a review of panel balance and NJ/PA coding: no edits.

---

# Your turn

*Your turn · Fri 09:35–09:55*

Open `.claude/agents/data-reviewer.md` and mark three things:

1. **The job:** what piece of work is this?
2. **The limits:** what bounds did we set?
3. **What it hands back:** a review. Name one other result a sub-agent can hand back.

---

# Rule of thumb: Skill or sub-agent?

*[Fri 09:55–10:15]*

> **In plain words:** Use a **Skill** when the same steps should be reused in place.  
> Use a **sub-agent** when the piece of work needs its own focus, its own files, or would crowd the main conversation.

**Think of it as:** the sample-restrictions checklist in this chat, versus a research assistant who redoes the sample, rebuilds the figure, or reviews the cleaning.

---

# Card–Krueger: two tasks

| Skill | Sub-agent |
| --- | --- |
| "Recompute the DiD the same way each time." | "Redo the sample, or rebuild the parallel-trends figure, and hand back the file." |

You set the bounds. Inside them, the sub-agent can decide. You still approve the merge.

---

<!-- Answer key: 1 Skill, 2 sub-agent, 3 Skill, 4 sub-agent, 5 Skill, 6 sub-agent. -->

# Your turn: sort six tasks

*Your turn · Fri 09:55–10:15 · then compare with a neighbour*

|  | Card–Krueger task | Skill or sub-agent? |
| --- | --- | --- |
| 1 | Recompute group means after every data change | |
| 2 | Check NJ/PA coding without seeing my code | |
| 3 | Write the sample-restrictions note the same way | |
| 4 | Review literature claims while I fix code | |
| 5 | Check the folder reproduces from a fresh start | |
| 6 | Review my pull request in its own conversation | |

---

# Slot 3 · Fri 10:15–12:00

| Clock | Block |
| --- | --- |
| 10:15–10:50 | Using sub-agents |
| 10:50–11:15 | Orchestrating sub-agents and swarms |
| 11:15–11:25 | Pause |
| 11:25–12:00 | Issue-board swarm: launch two cards |
| *12:00–14:00* | *Lunch: the agents keep working* |

---

# Using sub-agents

*[10:15–10:50]*

> **In plain words:** Name the sub-agent and the bounds for this piece of work. It works in its own conversation and hands back what the job needs. These two reviewers may only read; a review is what they hand back. You decide what to keep.

**Think of it as:** two research assistants. One reviews the cleaning, one checks the citations. Neither sees the other's notes.

---

# Card–Krueger: two reviews

`Use the data-reviewer sub-agent on examples/card-krueger-toy/. Read only. Report panel balance and NJ/PA coding.`

`Use the literature-reviewer sub-agent on the same folder. Read only. Check the claims against the references.`

- Two separate conversations: neither sees the other's review.
- Where they agree, look closer. Where they disagree, you decide.

---

# Your turn

*Your turn · 10:15–10:50*

1. Run both reviewers on the Card–Krueger folder.
2. Log one finding you accept and one you reject in `notes/orchestration_log.md`.
3. Check that no file changed.

Reviewer won't start? Paste its instructions into a fresh chat and say "read only".  
Guide: `demos/slot3_subagents_vc.md` · `exercises/07_slot3_subagents_vc.md`

---

# Orchestrating sub-agents and swarms

*[10:50–11:15]*

> **In plain words:** Orchestrating means splitting a job into parts, handing each part to a different agent, and putting the results back together. A swarm is many agents working at the same time; a human still makes the final call.

**Think of it as:** a PI running several RAs, each with their own files.

---

# Card–Krueger: a writer and a checker

**Writer** (documents the panel) + **Checker** (reviews literature claims) → **You** (read both, then merge)

- Different files: the two agents never edit the same lines.
- Rules for the pair: `examples/card-krueger-swarm/README.md`.

---

# Your turn: split the job

*Your turn · 10:50–11:15*

Split "replicate and extend Card–Krueger" into three jobs that share no files.

| Job | Files it may touch | Done when |
| --- | --- | --- |
| 1 | | |
| 2 | | |
| 3 | | |

Pause 11:15–11:25.

---

# Issue-board swarm

*[11:25–12:00]*

> **In plain words:** Each job is written as an issue, a to-do card on GitHub. Agents pick up cards marked ready, work in their own copy, and send back a pull request linked to the card for review.

**Think of it as:** a job board in a shared office: whoever is free takes the next card.

---

# Card–Krueger: two cards on the board

**ready** → **in-progress** → **needs-review** → **done**

- Card 1: `ck-data-cleaning`: check and document the panel.
- Card 2: `ck-parallel-trends-figure`: draw the before/after figure.
- Cards live in `examples/card-krueger-swarm/issues/`.
- Only you move a card to **done**.

---

# Your turn: launch before lunch

*Your turn · 11:25–12:00*

1. Cloud agent? First fill in `agent-harness/autonomous_agent_risk_card.md`.
2. Open the two cards as issues and mark them **ready**.
3. Start two agents, one per card (cloud, or two local windows).
4. Go to lunch. Back at 14:00 to review.

At most two cards live. No confidential files. Agents never merge.

---

# Slot 4 · Fri 14:00–16:30

| Clock | Block |
| --- | --- |
| 14:00–14:10 | Review what the swarm returned |
| 14:10–14:25 | Goals |
| 14:25–14:50 | Acceptance criteria: rewrite one card, relaunch |
| 14:50–15:50 | Verification and evaluation |
| 15:50–16:15 | Capstone: your own project |
| 16:15–16:30 | Close and 7-day plan |

---

# Review what came back

*[14:00–14:10]*

For each pull request from lunch:

1. Ask `pr-reviewer` (read only) for a report.
2. Did it touch only the files on its card?
3. Does the check command pass?
4. Move the card to **done**, or back to **ready** with a note.

**How did each agent know when to stop?**

---

# Goals

*[14:10–14:25]*

> **In plain words:** A goal is one sentence describing the finished state, in a form you can check. It tells the agent where to stop, not how to get there.

**Think of it as:** the destination in a satnav, not the turn-by-turn directions.

---

# Card–Krueger: from vague to checkable

> **Vague:** "Audit the replication."

> **Goal:** `notes/replication_audit_ck.md` exists and records GREEN, YELLOW or RED with the check output.

Claude Code and Codex: type `/goal` first. Cursor: make it the last line of the prompt.  
More goals: `examples/card-krueger-goals/goals/`

---

# Your turn

*Your turn · 14:10–14:25*

1. Take one lunchtime card.
2. Rewrite its title as a one-sentence goal.
3. Test: could a stranger answer "done?" with yes or no?

---

# Acceptance criteria

*[14:25–14:50]*

> **In plain words:** A yes/no check that says when a job counts as done. In a swarm, each agent knows when to stop, and you can check many results quickly.

**Think of it as:** a building inspector's checklist.

---

# Card–Krueger: done when…

Card `ck-data-cleaning` is done when:

- [ ] `toy_fast_food.csv` is unchanged.
- [ ] The check command passes.
- [ ] The README states the sample restriction.
- [ ] The DiD printed equals the DiD in the note.

Each line is yes or no. No line asks "is it good?"

---

# Your turn: rewrite and relaunch

*Your turn · 14:25–14:50*

1. Add three yes/no criteria to one card.
2. Relaunch the agent on that card.
3. Judge the new pull request only against your three lines.

Template: `templates/issue_card.md`

---

# Verification and evaluation

*[14:50–15:50]*

1. **Check less:** small jobs, protected files, clear done-when checks.
2. **Automate:** check commands that run on their own, on every change.
3. **Test your set-up:** try your Skills, sub-agents and whole set-up on known mistakes.

**Think of it as:** planting a known error in a paper to see whether the referee catches it.

---

# Card–Krueger: a planted mistake

`faults/drifted_table.tex`: a hand-copied DiD (3.15) and row count (47).

**1. Fail** (check stops) → **2. Diagnose** (which number?) → **3. Fix** (never the checks) → **4. Rerun** (check passes)

A passing check means the numbers match. It says nothing about causality.

---

# Card–Krueger: test the helpers

| What you test | Known mistake | Result |
| --- | --- | --- |
| Skill: `replication-checker` | `drifted_table.tex` | caught / missed |
| Sub-agent: `data-reviewer` | `unbalanced_panel.csv` | caught / missed |
| Whole set-up | Fresh chat, fresh copy: reproduce from the README alone? | yes / no |

Planted mistakes: `examples/card-krueger-toy/faults/`

---

# Your turn

*Your turn · 14:50–15:50*

1. On a temporary separate copy, fix one planted mistake.
2. Do not touch `tests/`. Rerun the check command.
3. Fill in the three-row scorecard: Skill, sub-agent, whole set-up.
4. Record it in `templates/agent_use_record.md`.

Optional demo: an automatic check after each edit (`.claude/hooks/`).  
Guide: `demos/slot4_verify_capstone.md`

---

# Capstone: your own project

*[15:50–16:15]*

On one non-confidential project of yours:

1. One rule in its `AGENTS.md`.
2. One Skill for a task you repeat.
3. One goal with three yes/no criteria.
4. Evidence: the check command and its output.

Only confidential data at hand? Use the Card–Krueger folder. Rubric: `docs/capstone_rubric.md`

---

# Close: your next seven days

*[16:15–16:30]*

- Day 1: add `AGENTS.md` to one real project.
- This week: turn one weekly chore into a Skill.
- Next job you delegate: write a goal and three done-when checks first.
- Always: read the list of changes; you sign off, not the agent.

Plan: `docs/adoption_plan_7d.md` · Start page: `START_HERE.md`
