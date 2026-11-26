# Concept map — EIEF / Luiss 8h

**Clock (Rome, do not change):** Thu 26 Nov 2026 09:00–12:00; Fri 27 Nov 2026 09:30–12:00 and 14:00–16:30.
**Course goal:** give an AI agent a research job with rules, a finish line and a check, and show a colleague the result reproduces.
**One example:** the synthetic Card–Krueger panel (`examples/card-krueger-toy/`). No research tracks.
**Rule:** each concept has a definition, an analogy, a Card–Krueger example and an exercise. Agents never certify identification or causality.

Concepts take 400 minutes; logistics and the Capstone take 80. Slot totals: 120, 60 + 45, 105 and 150 minutes.

## Slot 1: Thu 09:00–11:00

| Clock | Min | Block | Exercise |
| --- | ---: | --- | --- |
| 09:00–09:10 | 10 | Welcome, room rules, `python3 scripts/validate_setup.py` | — |
| 09:10–09:30 | 20 | Agent vs chatbot | `exercises/04_slot1_workflows.md` A |
| 09:30–09:55 | 25 | Version control (first pull request) | `exercises/04_slot1_workflows.md` B |
| 09:55–10:35 | 40 | `AGENTS.md` boundaries + privacy | `exercises/05_slot1_governance.md` A–B |
| 10:35–10:45 | 10 | Pause / setup rescue | — |
| 10:45–11:00 | 15 | To-do lists | `exercises/05_slot1_governance.md` C |

## Slot 2: Thu 11:00–12:00 + Fri 09:30–10:15

| Clock | Min | Block | Exercise |
| --- | ---: | --- | --- |
| Thu 11:00–11:25 | 25 | Skills: why | `exercises/06_slot2_sdd_skill_pr.md` A |
| Thu 11:25–11:55 | 30 | Create a Skill | `exercises/06_slot2_sdd_skill_pr.md` B |
| Thu 11:55–12:00 | 5 | Thursday wrap, overnight task | — |
| Fri 09:30–09:35 | 5 | Recap | — |
| Fri 09:35–09:55 | 20 | Sub-agent vs Skill | `exercises/06_slot2_sdd_skill_pr.md` C |
| Fri 09:55–10:15 | 20 | Rule of thumb: Skill or sub-agent | `exercises/06_slot2_sdd_skill_pr.md` D |

## Slot 3: Fri 10:15–12:00

| Clock | Min | Block | Exercise |
| --- | ---: | --- | --- |
| 10:15–10:50 | 35 | Using sub-agents | `exercises/07_slot3_subagents_vc.md` A |
| 10:50–11:15 | 25 | Orchestrating sub-agents and swarms | `exercises/07_slot3_subagents_vc.md` B |
| 11:15–11:25 | 10 | Pause | — |
| 11:25–12:00 | 35 | Issue-board swarm (launch; agents work over lunch) | `exercises/07_slot3_subagents_vc.md` C |

## Slot 4: Fri 14:00–16:30

| Clock | Min | Block | Exercise |
| --- | ---: | --- | --- |
| 14:00–14:10 | 10 | Review what the swarm returned | `exercises/08_slot4_verify_capstone.md` A |
| 14:10–14:25 | 15 | Goals | `exercises/08_slot4_verify_capstone.md` B |
| 14:25–14:50 | 25 | Acceptance criteria (rewrite one issue, relaunch) | `exercises/08_slot4_verify_capstone.md` C |
| 14:50–15:50 | 60 | Verification and evaluation | `exercises/08_slot4_verify_capstone.md` D |
| 15:50–16:15 | 25 | Capstone: rules file, Skill, goal, and acceptance criteria on own non-confidential project | `exercises/08_slot4_verify_capstone.md` E |
| 16:15–16:30 | 15 | Close + 7-day adoption plan | `docs/adoption_plan_7d.md` |

## Definitions

| Concept | Definition | Analogy |
| --- | --- | --- |
| Agent vs chatbot | A chatbot only talks. An agent can also act: it opens your files, runs your code, reads the result and tries again. | Phoning a friend vs an RA at your desk |
| Version control | A record of every saved version, each with a note. GitHub keeps it online and lets others review changes before they are accepted. | Track Changes plus dated "save as" copies |
| Rules file | A plain-text rules file the agent reads before any task: what it may touch, what it must never do, how to check its work. | House rules for a new RA |
| To-do lists | Before acting, the agent writes its steps as a checklist. You edit it, then it works through it. | A shopping list checked before driving |
| Skills | A repeatable set of instructions followed in the same conversation. | A checklist you follow in this chat |
| Create a Skill | A folder and one short file: name, when to use it, numbered steps. Test once, fix what was unclear. | Your referee checklist written down |
| Sub-agent vs Skill | Another agent you hand a piece of the work. It has its own conversation and its own instructions. Inside the bounds you set, it can read, write, check, and decide, and it hands back whatever the job needs. A summary is one possible result. | A research assistant who redoes the Card–Krueger sample, rebuilds the parallel-trends figure, or reviews the cleaning |
| Rule of thumb | Same steps reused in place → Skill. Own focus, own files, or it would crowd the main conversation → sub-agent. | The sample-restrictions checklist in this chat vs handing the sample, the figure, or the review to a research assistant |
| Using sub-agents | Name the agent and the bounds. It works in its own conversation and hands back what the job needs. The two morning reviewers may only read; a review is one result. | Two research assistants who review different parts and do not see each other's notes |
| Orchestrating | Split the job, hand each part to a different agent, put results together. A swarm is many agents at once; a human decides. | A PI running several RAs |
| Issue-board swarm | Each job is a GitHub issue; agents pick up `ready` cards and return linked pull requests. | A job board in a shared office |
| Goals | One sentence describing the finished state, in a form you can check. | A satnav destination |
| Acceptance criteria | A yes/no check that says when a job counts as done. | A building inspector's checklist |
| Verification | Need less checking, automate the rest, test your set-up against known mistakes. | Planting an error to test a referee |

Out of the room: MCP (optional prework). Teaching peek and research tracks are not part of this workshop.
