# Alien vs. native predator impacts meta-analysis — update

Working repository for an **update of the meta-analysis** published by Salo et al. (2007),
*Alien predators are more dangerous than native predators to prey populations* (Proceedings of the
Royal Society B 274:1237–1243, doi:10.1098/rspb.2006.0444).

## Folder structure

| Folder            | Contents                                                                 |
|-------------------|--------------------------------------------------------------------------|
| `protocol/`       | Review/meta-analysis protocol and the summary of the original study.     |
| `references/`     | Bibliography (`alien_predator_meta.bib`, Zotero/Better BibTeX), PDFs, and `README_zotero.md`. |
| `data/input/`     | Raw / source datasets (treated as read-only).                            |
| `data/output/`    | Processed datasets, effect-size tables, derived results.                 |
| `analysis/`       | Analysis scripts (R), notebooks, and code.                               |
| `manuscript/`     | Manuscript drafts, figures, tables, supplementary materials.             |

## Status

- [x] Repository and folder structure created; version control initialized.
- [x] Summary of the original 2007 meta-analysis drafted — see
      [`protocol/01_summary_Salo_2007.md`](protocol/01_summary_Salo_2007.md).
- [x] Update protocol drafted (v0.1) — see
      [`protocol/02_update_protocol.md`](protocol/02_update_protocol.md). Contains `[TBD]` placeholders
      (co-authors, funding, pilot search results, decision trees) to resolve before pre-registration.
- [x] Source PDF and protocol template archived in [`references/`](references/).
- [ ] Reconstruct the original dataset from the electronic supplementary material and reproduce the
      published estimates (see protocol §3.1).
- [ ] Build benchmark set and run/report pilot searches; develop screening decision trees.

## Note on data availability

Unlike some more recent syntheses, Salo et al. (2007) did **not** deposit an open dataset in a
repository, and **no analysis code was published**. The primary data (the list of included studies and
their extracted values) are contained in the paper's **electronic supplementary material** (Appendix S1,
tables S1 and S2; https://dx.doi.org/10.1098/rspb.2006.0444). The reproduction step therefore
**reconstructs** the analysis dataset from that supplementary material and **re-implements** the original
analyses (originally run in MetaWin 2.1, SAS 9.1, and S-Plus 6) in R before updating — rather than
re-executing archived data and code, which are not available.

## References

Citations are managed in **Zotero** with the **Better BibTeX** extension, auto-exported to
[`references/alien_predator_meta.bib`](references/alien_predator_meta.bib). The protocol cites with
Pandoc `[@key]` syntax and generates its reference list on render — do not edit the `.bib` or the
list by hand. Setup and rendering instructions are in
[`references/README_zotero.md`](references/README_zotero.md).

## Conventions

- Treat `data/input/` as immutable; all transformations write to `data/output/`.
- Analyses are scripted in R. The original used **MetaWin v. 2.1** (Hedges' *d*, `Q` homogeneity tests),
  **SAS v. 9.1** (Satterthwaite *t*-tests), and **S-Plus v. 6** (negative-binomial GLM); the update
  re-implements and extends these in R (e.g. the `metafor` package, `rma.mv`).
