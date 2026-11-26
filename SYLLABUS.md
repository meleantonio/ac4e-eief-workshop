# Syllabus — Agentic Coding for Economists (EIEF / Luiss)

**Instructor:** Antonio Mele\
**Audience:** Faculty and research staff at EIEF / Luiss; PhD and advanced Master's students if seats allow.\
**Dates:** Thu–Fri **26–27 November 2026**, Rome time.\
**Length:** Eight hours in four slots, across three booked blocks:

- **Thu 26 Nov:** 09:00–12:00
- **Fri 27 Nov:** 09:30–12:00 and 14:00–16:30

**Language:** English, with Italian Q&A as needed. **Recording:** allowed.

---

## Positioning

You already know how to supervise a research assistant: set the job, say which files they may touch, and check the output. This workshop teaches the same habits for an AI agent, in 14 short concepts. Each concept has a plain definition, an everyday analogy, one Card–Krueger example and a short exercise.

**What this is:** hands-on, one shared example, taught live in Claude Code with notes for Codex and Cursor.\
**What this is not:** a chatbot tutorial, a programming course, or training in causal inference.

---

## Prerequisites

A personal laptop with install rights if possible, a GitHub account, and one agent installed and signed in (Claude Code preferred; Codex or Cursor fine). See [`SETUP.md`](SETUP.md) and [`docs/prework.md`](docs/prework.md). No programming experience is assumed.

---

## Learning outcomes

By the end you can:

1. Explain the difference between a chatbot (only talks) and an agent (also opens files, runs code and tries again).
2. Make a separate copy, save a version with a note, open a pull request, review the list of changes and merge.
3. Write rules in an `AGENTS.md` file and decide, from sensitivity, permission and location, whether data may go near an agent.
4. Ask for a to-do list before any action, edit it, and let the agent run one step.
5. Run a Skill and explain why saved instructions beat retyped prompts.
6. Write, test and fix a Skill of your own.
7. Explain how a sub-agent (another agent with its own conversation that carries out a piece of work) differs from a Skill (repeatable instructions followed in the same conversation).
8. Decide whether a task calls for a Skill or a sub-agent.
9. Run two read-only sub-agents and decide which findings to accept.
10. Split a job into parts that share no files and assign them to different agents.
11. Run a small swarm from GitHub issues and review the pull requests it returns.
12. Write a goal: one checkable sentence describing the finished state.
13. Write yes/no acceptance criteria and judge an agent's work only against them.
14. Reduce, automate and test your checking, including against planted mistakes.

Agents never certify identification, causality or interpretation.

---

## Schedule

| Day | Clock | Slot | Concepts |
| --- | --- | --- | --- |
| Thu 26 Nov | **09:00–11:00** | 1 | Agent, version control, rules, to-do lists |
| Thu 26 Nov | **11:00–12:00** | 2 (part 1) | Skills |
| Fri 27 Nov | **09:30–10:15** | 2 (part 2) | Sub-agent vs Skill |
| Fri 27 Nov | **10:15–12:00** | 3 | Sub-agents and swarm (launch) |
| Fri 27 Nov | **14:00–16:30** | 4 | Swarm review, goals, criteria, verification, Capstone, close |

Minute-by-minute: [`SCHEDULE.md`](SCHEDULE.md).

---

## Running example

One example throughout: the synthetic Card–Krueger minimum-wage panel in `examples/card-krueger-toy/`. It is inspired by Card and Krueger (1994) but is not that paper's data. In the Capstone you switch to a **non-confidential** piece of your own work.

---

## Completion

You finish when you can show, with output from commands that ran:

- one `AGENTS.md` rule and a filled privacy check;
- one Skill you wrote, run once and fixed once;
- one goal with 3 acceptance criteria;
- one planted mistake caught and fixed, with the check command green again;
- a Capstone that passes [`docs/capstone_rubric.md`](docs/capstone_rubric.md), and a 7-day plan.

This is a workshop completion standard, not a certification of research quality.

---

## Tools

| Tool | Role |
| --- | --- |
| Claude Code | Live demos |
| Codex | Fully supported |
| Cursor | Fully supported |

The habits are the same across tools; only menus and folder names change ([`tool-lanes/`](tool-lanes/)).
