# Robustness checks for the Card–Krueger DiD

**Goal:** running `examples/card-krueger-toy/src/did_analysis.py` prints the main
DiD and two labelled robustness versions, each with its sample count.

Ask for the agent's to-do list only. Edit the list, then let it do step 1.

## What to do

Keep the main estimate (toy DiD 3.0) and add two versions:

1. **Trim:** drop rows above the 98th percentile of FTE employment (pooled over
   states and waves), then recompute.
2. **Completers:** after the trim, keep only stores with positive employment in
   both waves.

Each panel shows the NJ and PA means before and after, the NJ change, the PA
change, the DiD and the number of stores.

## Expected to-do list

1. Load the panel.
2. Check it is balanced.
3. Compute the group means and the main DiD.
4. Run the drop-store checks: the trim version, then the completers version.
5. Write a short README note on how each version changes the sample.

## Acceptance criteria (done when)

- [ ] Three labelled panels print, each with "synthetic teaching data" in its header.
- [ ] Each panel shows the four means, the DiD and the sample count.
- [ ] The main panel still prints 3.0.
- [ ] `git diff --stat examples/card-krueger-toy/data/` shows no changes, and the
      check command passes.

## Check command

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

Edit only `src/did_analysis.py`, `README.md`, and new checks in
`tests/test_did_analysis.py`. Never change existing checks. A trimmed estimate is
not more credible without an economic reason.
explain me what you have done
create a word file with main results
