# Guide

One page: the 14 concepts, the words we use, and the one example.

## The 14 concepts

| Concept | In one line | Where |
| --- | --- | --- |
| Agent vs chatbot | A chatbot talks; an agent also opens files, runs code and tries again. | Slot 1 |
| Version control | Every saved version with a note; GitHub adds review before changes are accepted. | Slot 1 |
| `AGENTS.md` + privacy | A rules file the agent reads first. Anonymize, authorize, keep it on the machine. | Slot 1 |
| To-do lists | The agent writes its steps first; you edit them before it acts. | Slot 1 |
| Skills | A repeatable set of instructions followed in the same conversation. | Slot 2 |
| Create a Skill | A folder, one short file: name, when to use it, numbered steps. | Slot 2 |
| Sub-agent vs Skill | A sub-agent is another agent, with its own conversation, that carries out a piece of work and hands back the result. A Skill stays in this conversation. | Slot 2 |
| Rule of thumb | Same steps reused in place → Skill. Own focus, own files, or it would crowd the chat → sub-agent. | Slot 2 |
| Using sub-agents | Name the agent and the bounds. A review, a file, or a figure can come back. | Slot 3 |
| Orchestrating | Split the job, hand out parts with no shared files, put results together. | Slot 3 |
| Issue-board swarm | Jobs as GitHub cards; agents return pull requests for review. | Slots 3–4 |
| Goal | One checkable sentence describing the finished state. | Slot 4 |
| Acceptance criterion | A yes/no check that says when a job counts as done. | Slot 4 |
| Verification | Need less checking, automate the rest, test your set-up on known mistakes. | Slot 4 |

## Words we use

| Word | Meaning |
| --- | --- |
| project folder | all the files plus their history (GitHub calls it a repository) |
| saved version | a snapshot of the files with a one-line note |
| separate copy | a branch: where edits happen without touching the main copy |
| list of changes | lines added (green) and removed (red) |
| pull request | a request to fold a separate copy into the main one, with a review page |
| issue | a to-do card on GitHub |
| `AGENTS.md` | the rules file |
| Skill | repeatable instructions followed in the same conversation |
| sub-agent | another agent you hand a piece of the work; it has its own conversation and hands back the result |
| swarm | a team of agents working at once |
| goal | a checkable finish line |
| acceptance criterion | a done-when check |
| check command | the command that runs the automatic checks |
| set-up | your rules + Skills + helpers + checks together |

## The example

[`examples/card-krueger-toy/`](examples/card-krueger-toy/) is a synthetic panel inspired by Card and Krueger (1994), not the paper's data. Its toy DiD is 3.0 FTE workers. Nothing computed from it is a research finding.

Check command:

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

## Safe default prompt

```text
Read [named files]. Do not edit any file. Explain what goes in, what comes out,
and which command checks it. Separate facts from guesses.
```

## Confidential data

Anonymize, authorize, keep it on the machine. In this room, only public or synthetic data. Agents never certify identification or causality.
