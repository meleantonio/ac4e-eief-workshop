# Reference — Exercise 07

## A. Two reviewers

Typical `data-reviewer` findings: the main panel is balanced (each store has one before and one after row); NJ is the treatment group and PA the comparison; the README should state the sample restriction more clearly.

Typical `literature-reviewer` finding: `faults/citation_mismatch.md` cites the toy DiD as Card and Krueger (1994). That claim is wrong; the file is synthetic.

Accept/reject example:

- **Accept:** the citation mismatch. The toy number is not the paper's.
- **Reject:** "add standard errors to the 2×2 table". The note says not to report precision for this teaching contrast.

## B. Three jobs, no shared files

| Job | Files it may change | Reviewer |
| --- | --- | --- |
| Document the panel and sample restriction | `examples/card-krueger-toy/README.md`, `examples/card-krueger-toy/data_notes.md` | `data-reviewer` |
| Draw the before/after group-means figure | `examples/card-krueger-goals/figures/` (script + figure) | `pr-reviewer` |
| Check literature claims | `references/bibliography.bib`, `notes/ck_literature_note.md` | `literature-reviewer` |

Not allowed: two jobs both editing `README.md`.

## C. Launch

- Two issues exist on GitHub, both labelled `in-progress`.
- Each agent works on its own separate copy and will open a pull request that mentions its issue number.
- Risk card filled before any cloud agent.

If cloud agents are not available: two local windows, each on its own separate copy, is a full answer.
