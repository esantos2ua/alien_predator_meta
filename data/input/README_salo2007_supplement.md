# Salo et al. 2007 — supplementary data

Source: Salo, Korpimäki, Banks, Nordström & Dickman 2007, *Alien predators are
more dangerous than native predators to prey populations*, Proc. R. Soc. B 274,
1237–1243 (doi:10.1098/rspb.2006.0444).

Extracted from the electronic supplementary material (Word `.doc` files):

| CSV | Source file | Content |
|-----|-------------|---------|
| `salo2007_replicated_studies.csv`   | `rspb20060444s02.doc` (Table S1) | 45 replicated studies; effect size = Hedges' *d* |
| `salo2007_unreplicated_studies.csv` | `rspb20060444s03.doc` (Table S2) | 30 unreplicated studies (35 rows; ref 15 = 6 cases); effect size = response ratio Xe/Xc |

The **full reference** for each row was taken from Appendix S1 (`rspb20060444s01.doc`)
and matched to the `reference_no` (references are numbered by list order in the
appendix, one number per study). Combined studies (e.g. experiments started in one
paper and reported in another) carry both citations in the `reference` field.

## Columns
- `reference_no` — study number as printed in the table (unreplicated ref 15 is split into `15 case 1`…`15 case 5`).
- `reference` — full source citation from Appendix S1.
- `class_prey`, `type_prey` — prey taxon class and functional type.
- `predator_prey_weight_ratio` — predator/prey body-weight ratio.
- `class_predator`, `origin_predator` (native/introduced), `location` (mainland/island), `continent`.
- `type_experiment` — SEC (simultaneous experimental & control) or BA (before-and-after).
- `treatment` — rem (predator removal), add (predator increase), or both.
- `exclosure_or_open` — exclosure or open.
- `spatial_scale_km2`, `temporal_scale_months`.
- `type_of_response` — reproduction, pop.size, or both.
- `effect_size` — value as printed.
- `effect_size_type` — `Hedges_d` (replicated) or `response_ratio_Xe_over_Xc` (unreplicated).

## Values preserved verbatim from the source (verify before analysis)
- Replicated ref **19**: `treatment` is printed as `em` in the original document
  (apparent typo for `rem`). Left unchanged.
- Unreplicated ref **15 case 3** and ref **25**: `spatial_scale_km2` was a lone `.`
  in the original (no value); recorded here as empty/missing.

Extraction tooling: `wvWare` (`wvHtml`) to preserve table cell boundaries
(macOS `textutil` flattened the tables and glued adjacent numeric columns).
