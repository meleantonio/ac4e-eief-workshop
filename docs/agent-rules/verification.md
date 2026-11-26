# Verification rules

Linked from [`AGENTS.md`](../../AGENTS.md).

## The check command

From the repository root:

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

On Windows: `python -m pytest ...`. Setup check for a new laptop:
`python3 scripts/validate_setup.py`.

## Expected teaching numbers

| Script | Expected output |
| --- | --- |
| `examples/card-krueger-toy/src/did_analysis.py` | NJ change 2.0, PA change −1.0, toy DiD 3.0 FTE |
| `examples/card-krueger-toy/src/panel_workflow.py` | Row counts 47, 43, 42, 36 (18 stores); baseline DiD 2.875 |

If a number differs, stop and report it. Do not change code or data to hit the number
without telling the human.

## What counts as evidence

- The command was **run in this session**, and its last lines (pass/fail counts) are
  quoted in the reply or PR.
- A claim like "tests pass" or "replication green" with no quoted output is not evidence.
- If a step could not be run, say so and say why.

## What a green check does not show

It shows the code reproduces the teaching numbers. It does **not** validate the
identification strategy, the interpretation, or any causal claim. Those need human review.

## Useful tools in this repo

- Skill `replication-checker`: assesses whether outputs reproduce from a clean setup.
- Sub-agent `loop-verifier`: one execute–evaluate–revise iteration with a pass/fail verdict.
- Planted errors in `examples/card-krueger-toy/faults/` for practising detection
  (use them only on a separate branch).
