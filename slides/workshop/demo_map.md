# Slide-to-demo map

Each of the fourteen ideas, its slides, and the files used live. One example throughout:
the synthetic Card–Krueger panel in `examples/card-krueger-toy/`.

Projector: `slides/workshop/workshop_slides.pdf` (source `workshop_slides.tex` + `slot1`–`slot4.tex`).
Marp copy: `slides/option_b_four_slots.md` (same 57 slides, same order).
Clock (Rome): Thu 26 Nov 09:00–12:00; Fri 27 Nov 09:30–12:00 and 14:00–16:30.
Demos stay at 15 minutes, hard cap 20.
Each slot's clock slide (pages 5, 20, 34, 44) is counted with the first block of that slot.

| Idea | Clock | Pages | Demo or action | Files |
| --- | --- | --- | --- | --- |
| Welcome | Thu 09:00–09:10 | 1–5 | Idea map, one example, room rules, `python3 scripts/validate_setup.py` | `START_HERE.md`, `scripts/validate_setup.py` |
| Agent vs chatbot | 09:10–09:30 | 6–8 | Same NJ–PA question in a plain chat and in the agent (read only) | `demos/slot1_workflows.md`, `exercises/04_slot1_workflows.md`, `examples/card-krueger-toy/src/did_analysis.py` |
| Version control | 09:30–09:55 | 9–12 | Separate copy → edit one line → saved version → pull request → review → merge | `sessions/slot1.md`, `demos/slot1_workflows.md`, `exercises/04_slot1_workflows.md`, `notes/lane_choice.md` |
| `AGENTS.md` + privacy | 09:55–10:35 | 13–16 | Agent refuses to edit `toy_fast_food.csv`; three privacy questions | `AGENTS.md`, `CLAUDE.md`, `.gitignore`, `docs/privacy_boundary.md`, `demos/slot1_governance.md` |
| Pause | 10:35–10:45 | — | Set-up help | `SETUP.md` |
| To-do lists | 10:45–11:00 | 17–19 | Plan only for the robustness-checks goal; edit the list; run step 1 | `examples/card-krueger-goals/goals/ck-robustness-checks.md`, `templates/agent_task_contract.md`, `notes/modes_playbook.md` |
| Skills: why | Thu 11:00–11:25 | 20–23 | Read, then run `replication-checker` on the Card–Krueger folder | `.claude/skills/replication-checker/SKILL.md`, `demos/slot2_sdd_skill_pr.md`, `exercises/06_slot2_sdd_skill_pr.md` |
| Create a Skill | 11:25–11:55 | 24–26 | Write `sample-restrictions-note`, run once, fix one step | `templates/skill_template.md`, `.claude/skills/sample-restrictions-note/SKILL.md`, `examples/card-krueger-toy/src/panel_workflow.py` |
| Wrap / recap | Thu 11:55–12:00, Fri 09:30–09:35 | 27 | Overnight: draft one Skill | `docs/between_sessions.md` |
| Sub-agent vs Skill | Fri 09:35–09:55 | 28–30 | Read `data-reviewer`: job, limits, what it hands back | `.claude/agents/data-reviewer.md` |
| Rule of thumb | 09:55–10:15 | 31–33 | Sort six Card–Krueger tasks into Skill or sub-agent | slide 33 (answer key in the source comment) |
| Using sub-agents | 10:15–10:50 | 34–37 | Run `data-reviewer` and `literature-reviewer`; compare reports | `.claude/agents/data-reviewer.md`, `.claude/agents/literature-reviewer.md`, `demos/slot3_subagents_vc.md`, `exercises/07_slot3_subagents_vc.md`, `notes/orchestration_log.md` |
| Orchestrating and swarms | 10:50–11:15 | 38–40 | Writer + checker on different files; split the job into three | `examples/card-krueger-swarm/README.md` |
| Issue-board swarm (launch) | 11:25–12:00 | 41–43 | Two cards marked ready; two agents run over lunch | `examples/card-krueger-swarm/issues/ck-data-cleaning.md`, `examples/card-krueger-swarm/issues/ck-parallel-trends-figure.md`, `docs/issues_tracking.md`, `agent-harness/autonomous_agent_risk_card.md` |
| Review | Fri 14:00–14:10 | 44–45 | `pr-reviewer` on each returned pull request | `.claude/agents/pr-reviewer.md` |
| Goals | 14:10–14:25 | 46–48 | Vague title → one-sentence goal (`/goal` in Claude Code and Codex; last prompt line in Cursor) | `examples/card-krueger-goals/README.md`, `examples/card-krueger-goals/goals/` |
| Acceptance criteria | 14:25–14:50 | 49–51 | Add three yes/no checks to a card; relaunch; judge only against them | `examples/card-krueger-swarm/issues/*.md`, `templates/issue_card.md` |
| Verification and evaluation | 14:50–15:50 | 52–55 | `drifted_table.tex` fail → diagnose → fix → rerun; score Skill, sub-agent, whole set-up | `examples/card-krueger-toy/faults/`, `demos/slot4_verify_capstone.md`, `exercises/08_slot4_verify_capstone.md`, `.claude/hooks/post_edit_did_analysis.py`, `templates/agent_use_record.md` |
| Capstone | 15:50–16:15 | 56 | rules file, Skill, goal, and acceptance criteria on own non-confidential project | `docs/capstone_rubric.md` |
| Close | 16:15–16:30 | 57 | Seven-day plan | `docs/adoption_plan_7d.md` |

## Build evidence

- PDF pages (`pdfinfo slides/workshop/workshop_slides.pdf | grep Pages`): **57**
- Beamer frames (`grep -c '\\begin{frame}' slides/workshop/*.tex`): **57** (`workshop_slides.tex` 4, `slot1.tex` 15, `slot2.tex` 14, `slot3.tex` 10, `slot4.tex` 14)
- Marp slides in `slides/option_b_four_slots.md`: **57**
- Build from `slides/workshop/`: `latexmk -pdf -interaction=nonstopmode workshop_slides.tex`, then `latexmk -c`.
