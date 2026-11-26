# Data and privacy rules

Linked from [`AGENTS.md`](../../AGENTS.md). Full privacy check: [`docs/privacy_boundary.md`](../privacy_boundary.md).

## Read-only data

- `examples/card-krueger-toy/data/*.csv` — synthetic panel, messy extract, chain table.
- Any `data/raw/` folder in a participant's own project.

If a task seems to require changing these files, stop and ask. Cleaning happens in
code (`src/panel_workflow.py`), never by editing the CSV.

## Do not open

- `data/private/`, `data/raw/` of a real project, `.env`, credential files.
- Confidential manuscripts, bank extracts, student records.

If asked to, refuse, quote this rule and point to `docs/privacy_boundary.md`.

## Documenting data work

Every transformation or sample restriction must be written down with:

- source file and unit of observation;
- the rule, and rows/stores left after it;
- units of any constructed variable (e.g. `fte_employment = ft + managers + 0.5 × pt`).

Record provenance in `templates/provenance_manifest.md`. Sample restrictions for the
toy panel are listed in `examples/card-krueger-toy/data_notes.md`.

## Research claims

- Separate what the code computes from what it means.
- Do not add standard errors, significance stars or causal language to toy-panel output.
- Citations must be checked against `references/bibliography.bib`; never invent a source.

## Cloud or autonomous agents

Fill in `agent-harness/autonomous_agent_risk_card.md` first. Default: anonymize,
get authorization, keep data on the machine.
