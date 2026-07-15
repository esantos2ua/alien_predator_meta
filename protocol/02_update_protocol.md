# 1. Study Protocol: Update of Salo et al. (2007)

## 1.1. Version history

- **Version 0.1** (13 Jul, 2026) — Eduardo S. A. Santos
  - Initial draft of update protocol (adapted from the mate-choice-copying update protocol template and the parallel `exotic_impact_meta` protocol)
- **Version 0.2** (13 Jul, 2026) — Eduardo S. A. Santos
  - Reproduce/replicate-then-update design adapted to the absence of open data/code: Q0 reconstructs the dataset from the electronic supplementary material (tables S1/S2) and re-implements the MetaWin/SAS/S-Plus analyses in R (with a ~10% validation re-extraction) rather than re-executing an archive
- **Version 0.3** (13 Jul, 2026) — Eduardo S. A. Santos
  - Added Q1a (geographic generality / Australia dominance) and Q1b (island vs. mainland) as explicit sub-questions; specified a unified effect-size framework (lnRR/SMD in multilevel `rma.mv`) to replace the split Hedges'-_d_ / raw-ratio approach; added study-design and region moderators
- **Version 0.4** (14 Jul, 2026) — Eduardo S. A. Santos
  - Aligned methods with the `mate_choice_meta` update: explicit effect-size conversion between currencies (with flagging of converted/reconstructed values); concrete predator- and prey-phylogeny workflow (Open Tree of Life) and multilevel random-effect/VCV structure replacing the original's species-averaging; formal reconstruction-validation statistics; a bias-corrected-mean estimation step (two frameworks) and dedicated leave-one-out sensitivity analyses; explicit PRISMA-EcoEvo adherence; strengthened multilingual/grey-literature search; commitment to report deviations from the pre-registration
- **Version 0.5** (15 Jul, 2026) — Eduardo S. A. Santos
  - Added conceptual/theoretical revisions: reframed the origin contrast as a proxy for evolutionary novelty and added **Q1c**, an a-priori filter-effect test (effect vs. time since establishment); added §2.2 interpretive-scope caveats (transient vs. equilibrium; effect size ≠ extinction risk; origin as proxy; few alien species; naiveté as one mechanism; management-site selection bias); added pre-specified origin-coding rules for range-shifters/subsidised natives, with supporting Table 2 fields and an origin-flag sensitivity analysis


## 1.2. Title

Alien predators are more dangerous than native predators to prey populations: Protocol for the update of a
meta-analysis.

## 1.3. Authors

- Eduardo S. A. Santos<sup>1a</sup>, ESAS, orcid: 0000-0002-0434-3655
- [TBD — co-authors to be confirmed]

## 1.4. Affiliations

<sup>a</sup> Department of Biological Sciences, Faculty of Science, University of Alberta, Edmonton, AB, Canada

<sup>1</sup> Corresponding author: esantos2@ualberta.ca

## 1.5. CRediT authorship contribution statement

- ESAS: Conceptualization, Methodology, Investigation, Data curation, Formal analysis, Visualization, Writing – original draft, Writing – review and editing, Project administration.
- [TBD]

## 1.6. Declaration of Generative AI and AI-assisted technologies in the writing process

During the preparation of this work, the authors used AI-assisted tools to check grammar, spelling, and reference formatting, and to support code development. After using these tools, the authors carefully reviewed and edited the content as needed. The authors take full responsibility for the content of this report.

## 1.7. Data availability statement

All relevant data and analysis code will be made available in a publicly accessible repository (e.g., Borealis, https://borealisdata.ca/, and/or the Open Science Framework). Unlike the original study, Salo et al. (2007) did not deposit an open dataset and published no analysis code; the primary data are contained in the paper's electronic supplementary material (Appendix S1, tables S1 and S2; https://dx.doi.org/10.1098/rspb.2006.0444). We will reconstruct the analysis dataset from that supplementary material for the reproduction step and archive the reconstructed dataset alongside our updated data and code.

## 1.8. Competing interests statement

The authors have declared that no competing interests exist.

## 1.9. Funding

[TBD — confirm funding sources. ESAS is supported by the Canada Excellence Research Chairs (CERC) program (grant number CERC-2022-00074).]

---

# 2. Background

Alien (introduced) predators are widely regarded as one of the foremost causes of native-species declines
and extinctions, with especially destructive effects reported for insular ecosystems, where prey are often
naive to the hunting tactics of novel predators. An older paradigm (Errington 1956) held that _native_
vertebrate predators do not depress prey population sizes because they take mainly surplus, non-reproductive,
or "doomed" individuals (compensatory mortality). Over subsequent decades this view softened: native
predators are now known to limit or regulate prey populations and occasionally to obliterate them locally.
Yet the **prevailing dogma** — that _alien_ predators are far more detrimental to native prey than native
predators — had, until Salo et al. (2007), not been critically and quantitatively evaluated (Gurevitch &
Padilla 2004).

Salo et al. (2007, _Proceedings of the Royal Society B_ 274:1237–1243, doi:10.1098/rspb.2006.0444) provided
the first explicit quantitative test of that dogma. From a worldwide search of field experiments in which the
densities of avian and mammalian predators had been manipulated, they assembled **45 replicated** and **35
unreplicated** experiments (80 experimental manipulations in total) and analysed the responses of vertebrate
(bird and mammal) prey. Using **Hedges' _d_** and categorical/continuous meta-analysis (MetaWin v. 2.1) for
the replicated set, ratio-based tests for the unreplicated set, and a pooled negative-binomial GLM (S-Plus),
they found that **predator origin had a highly significant effect on prey**: introduced predators suppressed
prey populations roughly **twice** as strongly as native predators, and the **origin × location** interaction
was significant. Effects were strongest for **alien predators on the Australian mainland**. Contrary to
expectation, they found **no support** for greater alien-predator impacts on islands than on the mainland.
They interpreted the results via **prey naiveté** and the **"filter effect"** (surviving prey being relatively
resistant to ongoing impacts) and concluded that alien predators can hold prey further below their
predator-free densities, increasing extinction risk. A full summary is provided in
[`01_summary_Salo_2007.md`](01_summary_Salo_2007.md).

Several features of the original make it a strong candidate for an update. First, its conclusion that alien
predators are more dangerous rests heavily on **Australian experiments**: the authors state plainly that few
alien-predator experiments existed from other regions and **none from mainland situations outside Australia**,
so the large overall alien effect is driven mainly by consistently high Australian effect sizes. Whether the
alien > native pattern **generalises beyond Australia** is therefore an open question that ~20 years of
additional experiments may now be able to answer. Second, the analysis used **two incompatible effect-size
currencies** — Hedges' _d_ for replicated studies and a raw ratio X_e/X_c for unreplicated studies, pooled via
a negative-binomial GLM — a patchwork that modern multilevel meta-analysis can unify. Third, **publication
bias** was assessed only for the replicated subset (normal quantile plot). Fourth, the primary data live only
in the **electronic supplementary material** with **no open code**, so reproduction requires reconstructing
the dataset and re-implementing the analyses. Finally, the search ended in **January 2006**, predating nearly
two decades of predator-manipulation experiments, including many more mainland, non-Australian alien-predator
studies.

Beyond these methodological features, the original leaves a **conceptual** question only partly examined, and the
~20 years since have sharpened both the theory and the evidence base — including the authors' own follow-up
meta-analysis (Salo et al. 2010) and a global synthesis implicating invasive predators in a large share of recent
vertebrate extinctions (Doherty et al. 2016). The original's mechanism — **prey naiveté** (Banks & Dickman 2007;
Sih et al. 2010; Carthey & Banks 2014) and the **filter effect** (Pimm et al. 1995; Cox & Lima 2006) — concerns
the **evolutionary novelty** of the predator to the prey's lineage, for which "introduced vs. native" is only a
proxy.
The two can diverge: an introduced predator sharing a continental archetype with a native one may not be novel,
whereas a range-shifting or human-subsidised "native" can be. In the original data, moreover, "alien" is closely
confounded with **eutherian, generalist, mammalian** predators (chiefly the red fox and cat), so the origin
contrast partly reflects predator taxonomy and hunting mode rather than origin as such. Crucially, the filter
effect makes a **directional, testable prediction the original never tested**: if naive prey are progressively
filtered out, the suppressive effect of an alien predator should **decline with time since its establishment**.
The ~20 years of additional experiments make this prediction — and a reading of the origin effect as an
evolutionary-novelty gradient — newly testable.

Foundational evidence syntheses should be reproduced, replicated, and updated. **Reproducing** re-uses (or, as
here, reconstructs) the original data and analysis to verify accuracy; **replicating** tests the same question
with new data and/or methods; **updating** incorporates newly available evidence to test whether conclusions
hold over time, draws on a larger and more diverse evidence base, and allows newer, more robust analytical
methods to be applied. Given the ~20 years elapsed since the original search, the accumulation of
non-Australian alien-predator experiments, and methodological advances in multilevel meta-analysis, an update
is warranted.

## 2.1. Aims and questions

Our overarching aim is to **update Salo et al.'s (2007) meta-analysis** of the relative impacts of alien
versus native predators on vertebrate prey, by (i) reproducing/replicating the original analysis from its
electronic supplementary material, then (ii) updating the synthesis by integrating new sources, new data, and
contemporary meta-analytic methods.

Our specific aim and research questions (Q) are:

- **Aim 1:** Reproduce/replicate Salo et al. (2007) and then update it by expanding the evidence base and
  applying contemporary analytical methods.
  - **Q0 (reproduce/replicate):** Can we recover the original published estimates by reconstructing the
    dataset from the electronic supplementary material (tables S1/S2) and re-implementing the original
    analyses (MetaWin Hedges' _d_ and homogeneity tests; the ratio-based unreplicated analysis; the pooled
    negative-binomial GLM) in R? This provides the baseline against which the update is compared.
  - **Q1 (update):** When we update the synthesis — adding **more sources** (additional databases; broader,
    non-English terms), **new data** (any eligible experiment not represented in the original dataset — both
    experiments published since the 2006 search _and_ older experiments the original missed, e.g. non-English or
    grey-literature studies within the pre-2006 window), and **updated methods**
    (a single multilevel model with an explicit taxonomic/phylogenetic random structure, robust variance
    estimation, and modern heterogeneity decomposition) — do the original main findings still hold? That is:
    alien predators suppress prey populations more than native predators; reproductive responses exceed
    population-size responses; and impacts are not greater on islands than on the mainland.

We will **not** re-extract every original study _de novo_. Instead, we reconstruct the archived tables S1/S2,
independently re-extract a **~10% sample** of them to validate the reconstruction (see _Data extraction_), and
add newly extracted effect sizes from the new evidence.

Within Q1 we additionally revisit two open issues from the original study:

- **Q1a (geographic generality / Australia dominance):** Does the alien > native conclusion hold **beyond
  Australia**? The original signal was dominated by Australian mainland experiments, with none from
  non-Australian mainlands. We treat **region/continent (and an Australia indicator)** as an explicit
  moderator and run sensitivity analyses excluding Australian studies, testing whether the contrast persists
  now that more non-Australian evidence exists.
- **Q1b (island vs. mainland):** The original found **no** greater impact on islands than the mainland — but
  this test was confounded by Australia being classed as mainland while sharing island-like characteristics.
  With more and better-distributed data we re-examine the **location × origin** interaction, disentangling
  the island signal from the Australian signal.
- **Q1c (evolutionary novelty / filter effect):** Because "introduced vs. native" is a proxy for the predator's
  **evolutionary novelty** to the prey (the mechanism the original invokes but does not measure), we test the
  filter effect's directional prediction that, **among alien-predator experiments, the suppressive effect
  declines with time since the predator's establishment** at the study region. We treat **time since
  introduction/establishment** as an a-priori moderator (a negative slope supports the filter effect), and
  interpret the origin contrast (Q1a) as the extreme of an evolutionary-novelty gradient rather than a binary.
  Where establishment dates are unavailable or too sparsely reported, this test is reported as exploratory and
  the limitation stated (see _Data synthesis_).

Where data permit, we will also explore additional moderators (e.g., predator/prey weight ratio, habitat,
climate context) as **exploratory extensions**, not core replication targets.

Table 1 summarises how search strategy, included evidence, and analytical models differ between the original
study (the Q0 baseline) and the update (Q1).

**Table 1. Structured comparison of the original study and the planned update.**

| Elements               | Original (Salo et al. 2007; Q0 baseline)                                                   | Update (Q1)                                                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Search / data strategy | Web of Science + Biosis Previews + Biological Abstracts; search ended January 2006         | More comprehensive: Web of Science + Scopus + supplementary sources; broader, non-English terms; no date restriction                              |
| Included studies       | 45 replicated + 35 unreplicated experiments (80 total), published 1939–2006                | Original experiments + all newly eligible experiments (post-2006 **and** pre-2006 records the original missed, incl. non-English/grey literature) |
| Effect-size currency   | Hedges' _d_ (replicated); raw ratio X_e/X_c (unreplicated); negative-binomial GLM (pooled) | Single unified currency (lnRR/SMD) in one multilevel model; study design (replicated vs. unreplicated) as a moderator                             |
| Analytical models      | MetaWin (Q homogeneity); SAS Satterthwaite _t_-tests; S-Plus `glm.nb`                      | Multilevel `rma.mv` (added taxonomic/phylogenetic + site random effects), robust variance estimation, modern heterogeneity decomposition          |
| Overall                | Original synthesis                                                                         | One integrated update combining new sources, new data, and updated methods                                                                        |

## 2.2. Interpretive scope and a priori caveats

We record the following interpretive commitments _before_ seeing the updated results, to constrain how the
findings will be read:

- **What the effect size measures.** A predator-manipulation effect size is a **transient response over the
  experiment's duration**, not a new equilibrium density, and it is **not** a direct measure of extinction risk.
  We will therefore describe results as _suppression of prey demographic rates_ and avoid equating a large
  standardised effect with conservation "danger" or with population regulation (the compensatory-vs-additive
  mortality question the original does not resolve). Experiment **duration** is retained as a moderator partly
  for this reason.
- **Origin is a proxy, not a mechanism.** The alien > native contrast (Q1a) will be interpreted as the extreme
  of an **evolutionary-novelty gradient** (Q1c), not as evidence for "introduced status" per se, because origin
  is confounded with predator taxonomy, diet breadth, and hunting mode in the evidence base.
- **The origin effect rests on few alien species.** In the original, the alien signal derived from a small number
  of species (chiefly red fox and cat). We will report the number of distinct alien predator species contributing
  to each estimate and, via the species/phylogenetic random effects, temper any generalisation to "alien
  predators" as a class.
- **Naiveté is one of several mechanisms.** Alternative explanations for alien > native cannot be fully separated
  with these data — e.g. release from the predator's own natural enemies (Colautti et al. 2004), subsidy of alien
  predators by alien prey (hyperpredation; Courchamp et al. 2000), and the release of alien mesopredators where
  native apex predators are absent or removed (mesopredator release; Prugh et al. 2009; Ritchie & Johnson 2009;
  Letnic et al. 2012), which can even make removing a _native_ predator increase prey suppression. The Discussion
  will treat prey naiveté as one hypothesis among several rather than the default.
- **Selection bias the funnel plots cannot see.** Alien-predator removals are frequently management interventions
  at sites where impact is already suspected, whereas native-predator manipulations are more often basic ecology.
  This design asymmetry can inflate the alien effect independently of publication bias; we flag it as a limitation
  our quantitative bias diagnostics (§3.10) do not address.

---

# 3. Methods

## 3.1. Protocol, registration, and reproduction

This study protocol will be submitted for pre-registration on the Open Science Framework (OSF). [Registration
DOI: TBD] Throughout the review and analysis we will adhere to the **PRISMA-EcoEvo** reporting standard for
systematic reviews and meta-analyses in ecology and evolutionary biology (O'Dea et al. 2021), completing and
archiving the PRISMA-EcoEvo checklist alongside the manuscript, and we will report any **deviations from this
pre-registered protocol** in a dedicated "additions and deviations" section of the final paper.

Because the original study published **no open dataset and no analysis code**, we cannot re-execute an
archive. The reproduction step (Q0) therefore proceeds in two parts: (i) **reconstruct** the analysis dataset
by digitising the electronic supplementary material (Appendix S1; table S1 = 45 replicated experiments; table
S2 = 35 unreplicated rows), including the coded study traits and the extracted means/dispersions/sample sizes;
and (ii) **re-implement** the original analyses in R — the MetaWin categorical/continuous meta-analysis of
Hedges' _d_ with random effects and 4999-iteration resampling, the Satterthwaite _t_-tests on the unreplicated
ratios, and the pooled negative-binomial GLM with `stepAIC`/AIC_c model selection — and check that the
published estimates (e.g. the _Q_\_M contrasts, the ~2× alien-vs-native effect, the Australian effect, and the
GLM deviance results) are recovered. Any discrepancies will be documented. The reproduction provides the
baseline against which the updated dataset and methods are compared.

## 3.2. Ethics and dissemination

As this update of a meta-analysis constitutes a summary and analysis of published literature, ethics approval
is not required. The results of this study will be published in a peer-reviewed journal.

## 3.3. PECOS scope and eligibility criteria

The objective is to update Salo et al.'s (2007) meta-analysis of the relative impacts of alien versus native
predators on vertebrate prey (see _Aims and questions_, above). Under the PECOS framework (Richardson et al.
1995; Foo et al. 2021), our main eligibility criteria are:

**Population:** Native vertebrate prey populations — avian or mammalian — whose demographic responses
(population size or reproduction) are measured.

**Exposure:** Experimental **manipulation of predator density** — either **addition** (release or attraction of
predators) or **removal/reduction** (exclosure, culling, or relocation) of avian or mammalian predators. The
predator is classified as **native or introduced (alien)** following each study's definition, confirmed
against a standard reference (e.g., Long 2003).

_Classifying origin in ambiguous cases._ Because the native/alien boundary is fuzzier now than in 2007, we
pre-specify the following coding rules: (i) a predator **translocated or introduced by humans** beyond its
historical range is coded **introduced**, even if native to the same country/continent; (ii) a predator that has
**expanded its range naturally** (e.g. climate-driven) into contact with the focal prey is coded **native** but
**flagged as a range-shifter** in a note field; (iii) a native predator whose density is **elevated by human
subsidy** (supplementary food, human-modified landscapes) is coded **native** but flagged as **subsidised**. Where
a study's own designation conflicts with these rules, we follow the rules and record the discrepancy. Range-shifter
and subsidised flags are used only in sensitivity analyses, not the primary origin contrast. Where reported, we
also record the **year/date of the predator's establishment** at the study region (for the Q1c filter-effect test).

**Comparator:** A control condition differing in predator density from the treatment — e.g., predator-removal
vs. predator-present areas, predator-addition vs. unmanipulated areas, or a before-and-after contrast.

**Outcomes:** Quantitative **prey demographic responses**, classified as **population size** (density, minimum
number known alive, breeding pairs, rate of increase/survival, catch-per-unit-effort) or **reproductive**
(numbers of juveniles/broods, females with young, survival of young, mean recruitment). _Per capita_ measures
(e.g. brood size, fledglings per pair) are excluded, as in the original.

**Study design:** Field experiments — **replicated** (≥ 2 control and ≥ 2 treatment units, or a
before-and-after design) or **unreplicated** (single treatment and/or control unit) — that report (or allow
calculation of) the quantities needed for an effect size and that ran long enough (**≥ 1 prey generation**)
for a demographic response.

Following and extending the original selection criteria, our criteria are:

1. The study experimentally **manipulates the density of avian or mammalian predators** (addition or removal)
   and measures a **native avian or mammalian prey** demographic response (livestock and other non-native prey
   excluded).
2. If both native and introduced predators were manipulated, the study is **included only if the effects of
   the two predator groups can be separated**; otherwise excluded.
3. The prey response falls in the **population-size** or **reproductive** categories above (not _per capita_).
4. The experiment ran for **≥ 1 prey generation**.
5. For each contrast, the study reports (or allows calculation of) a **mean, a dispersion measure (SD/SE/CL),
   and the number of replicates** (dispersion/replication may be absent only for unreplicated studies, which
   are analysed separately as in the original).
6. Records may be in any language; non-English records will be processed as described in _Information sources_.

### 3.3.1. Data-structuring rules (carried over from the original, for comparability)

- Multiple prey species within one study → use the **mean effect size across species** (to retain
  independence), as in the original; where the updated multilevel model can accommodate them, record species
  as separate rows nested within study (documented in _Data synthesis_).
- Reproductive responses recorded **separately per year**, then averaged to one effect size per study.
- **End-of-experiment** values used where possible; otherwise an arithmetic mean of responses over the study.
- **Cyclically fluctuating** prey (e.g. some small mammals) → values taken from the **peak phase** of the cycle
  for consistency.
- A study that both added and removed predators → a **single mean effect** for the whole study.
- Asymmetrical error bars → variance computed conservatively from the **longest bar**; if no variance is given,
  computed from raw results.

### 3.3.2. Exclusion criteria

We will exclude records that: (1) do not experimentally manipulate predator density; (2) confound native and
introduced predator effects that cannot be separated; (3) measure only _per capita_ or non-demographic
responses, or run for less than one prey generation; (4) provide no extractable mean (and, for replicated
studies, no dispersion/sample-size information and no raw data from which to compute them); or (5) are
reviews/models/opinion pieces reporting no new primary quantitative data (reviews will be screened for primary
references).

## 3.4. Information sources

We will reproduce the original searches in **Web of Science Core Collection**, **Biosis Previews**, and
**Biological Abstracts** (the original's databases) and, to broaden coverage, additionally search **Scopus** and
supplementary sources for grey and non-English literature: the **Scientific Electronic Library Online (SciELO)**,
the **Bielefeld Academic Search Engine (BASE)** for unpublished theses and grey literature, and **Google
Scholar** (run with `Publish or Perish`; Harzing 2007, sorted by relevance, records not numerically capped per
language). We will **not** impose language restrictions: search strings will be **translated** and the results
screened by **reviewers with expertise in the respective languages**, following the multilingual, grey-literature–
inclusive strategy used in the parallel `mate_choice_meta` update (where ~45% of newly found studies fell _within_
the original search window, confirming the value of this approach for recovering evidence the original missed).
[Languages and reviewer assignments: TBD.] We will also: (i) screen reference lists and citing articles of the
original and of key included studies and earlier reviews (backward/forward snowballing; the original mined Côté &
Sutherland 1997 and Newton 1998); (ii) consult relevant databases of introduced species and predator-management
literature; and (iii) contact authors for unreported but apparently collected data, as the original did.

## 3.5. Search strategy

We will validate search sensitivity using a benchmarking / relative-recall approach (Lagisz et al. 2025)
against a benchmark set of known eligible studies assembled **before** running searches (drawn from the
original's 80 experiments plus post-2006 literature). [Benchmark set: TO BE COMPLETED — see future
`03_benchmark_set.md`.]

**Original keyword set (the Q0 baseline; reproduced from the paper):** combinations of the keywords

```
introduced; alien; feral; predator; predation; experiment; manipulation;
removal; reduction; control; effect; impact
```

searched across Web of Science, Biosis Previews, and Biological Abstracts, supplemented by the bibliographies
of earlier reviews (Côté & Sutherland 1997; Newton 1998) and of retrieved papers.

> **Note on the keyword set.** The original reports keyword _combinations_ rather than a single verbatim
> Boolean string. For the update we will construct explicit, reproducible Boolean strings per database from
> these terms — a predator/manipulation concept block (`introduced OR alien OR feral OR ... AND predator* OR
predation AND experiment* OR manipulat* OR removal OR reduction OR exclos* ...`) crossed with an
> effect/impact block — and broaden the term sets (e.g. add _non-native_, _invasive_, _culling_, _translocation_,
> prey-response terms), then check relative recall against the benchmark set.

> **Pilot status: TO BE COMPLETED.** Before finalizing the protocol for pre-registration we will run pilot
> searches in each database and report, per database: access date, exact query (adapted to database syntax),
> total records retrieved, publication-date span, and relative recall against the benchmark set. The update
> (Q1) search carries no date restriction; new evidence is identified as records not already represented in
> the reconstructed original dataset.

### 3.5.1. Web of Science Core Collection

- Access date: [TBD]
- Query: [TBD — `TS = ( ... )` form]
- Total records retrieved: [TBD]
- Publication dates: [TBD]
- Relative recall: [TBD]

### 3.5.2. Scopus

- Access date: [TBD]
- Query: [TBD — `TITLE-ABS-KEY ( ... )` form]
- Total records retrieved: [TBD]
- Publication dates: [TBD]
- Relative recall: [TBD]

### 3.5.3. Biosis Previews / Biological Abstracts

- Access date: [TBD]
- Query: [TBD]
- Total records retrieved: [TBD]
- Publication dates: [TBD]
- Relative recall: [TBD]

## 3.6. Study selection

We will export and **deduplicate** retrieved records, and remove records already represented in the
reconstructed original dataset so that screening focuses on **new evidence**. Records will be randomly assigned
to the team for screening; records passing full-text screening proceed to data extraction, where their effect
sizes are added to the reconstructed dataset to form the updated dataset (Q1).

## 3.7. Screening

We will conduct **two-stage screening** in **Rayyan** (Ouzzani et al. 2016): (1) title/abstract/keywords, then
(2) full text, each assessed by **at least two independent reviewers** (blind mode), guided by decision trees
(Figures 1 and 2 — _to be developed_). Disagreements are resolved by discussion, with a third reviewer as
moderator. A pilot screening exercise will estimate inter-reviewer agreement and refine the decision trees.
[Pilot results: TBD]

**Figure 1.** Screening decision tree for title/abstract/keywords (first-stage). _[To be developed]_

**Figure 2.** Screening decision tree for full texts (second-stage). _[To be developed]_

## 3.8. Data extraction

We will extract effect-size data from text, tables, supplementary materials, and figures. Values in figures will
be digitised with **metaDigitise** (Pick et al. 2019); where an LLM-assisted figure-extraction routine is used to
speed extraction (as in the parallel `mate_choice_meta` update), its output will be **validated against
metaDigitise on a subset of ~20 records** and the agreement reported quantitatively (e.g., mean signed _z_-score
with 95% CI), with the routine adopted only if agreement is acceptable. (The original used data taken from text,
tables, and figures without a named digitiser.) At least **10%** of newly extracted records will be independently
and blindly re-extracted by a second reviewer; discrepancies resolved by discussion, and inter-extractor
agreement reported. For comparability with the original, we retain its coded study traits and add fields needed
for the updated analysis. Variables that cannot be extracted will be coded "NA". Effect sizes that are
**converted** between metrics or **reconstructed** from the supplementary material (rather than directly
calculated) will be flagged in a provenance field (see Table 2) so they can be isolated in sensitivity analyses.

**Reconstructing and validating the archive.** Because there is no deposited dataset, we first **reconstruct**
the original dataset by transcribing tables S1 (replicated) and S2 (unreplicated) from the electronic
supplementary material into the structure of Table 2 below. To verify the reconstruction and quantify any
transcription/extraction drift, we will independently re-extract a **random ~10% sample** of those studies from
their original source articles under the present protocol, and compare the re-extracted values against the
transcribed table. Following the validation approach of the parallel `mate_choice_meta` update (and the
validation-codebook logic of Sánchez-Tójar et al. 2018), agreement will be assessed **quantitatively** — for
means, dispersion, sample sizes, and the resulting effect size — using correlation, an OLS slope, and
**Bland–Altman limits of agreement**, and each discrepant record will be **classified by cause** (e.g.,
transcription error, different outcome extracted, different effect-size partitioning, dispersion/variance
handling). Material discrepancies will be documented and, if systematic, will trigger a wider re-extraction.

**Table 2. Core data to be extracted from each eligible experiment.**

| Variable                    | Description                                                                          | Data type; options; examples                                                                         |
| --------------------------- | ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| identifierExtractor         | Initials of the data extractor                                                       | Restricted; ESAS / …                                                                                 |
| identifierStudyId           | First author + year + source                                                         | Free text; Salo_2007_ProcRSocB                                                                       |
| identifierStudyYear         | Publication year (online if differs from print)                                      | Numeric (4 digits); 2007                                                                             |
| identifierStudyDoi          | DOI of the study                                                                     | Free text; 10.1098/rspb.2006.0444                                                                    |
| dataProvenance              | New extraction vs. carried over from the original supplementary material             | Restricted; New / Archived                                                                           |
| studyDesign                 | Replicated vs. unreplicated design                                                   | Restricted; Replicated / Unreplicated                                                                |
| predatorSpecies             | Manipulated predator species (binomial)                                              | Free text; Vulpes vulpes                                                                             |
| predatorOrigin              | Origin of the manipulated predator (per coding rules in §3.3)                        | Restricted; Native / Introduced                                                                      |
| predatorOriginFlag          | Ambiguous-origin flag for sensitivity analyses                                       | Restricted; None / Range-shifter / Subsidised                                                        |
| predatorEstablishmentYear   | Year the (introduced) predator became established at the study region, if reported   | Numeric (4 digits) or NA                                                                             |
| timeSinceEstablishment      | Years from predator establishment to the experiment (for the Q1c filter-effect test) | Numeric (years) or NA                                                                                |
| predatorClass               | Taxonomic class of the predator                                                      | Restricted; Mammal / Bird / Both                                                                     |
| preySpecies                 | Focal native prey species (binomial) or assemblage                                   | Free text; Petrogale lateralis                                                                       |
| preyClass                   | Taxonomic class of the prey                                                          | Restricted; Bird / Mammal                                                                            |
| preyType                    | Prey type / group                                                                    | Restricted; Rodent / Ungulate / Marsupial / Waterfowl / Other                                        |
| responseType                | Category of prey demographic response                                                | Restricted; Population size / Reproduction                                                           |
| responseMetric              | Specific metric measured                                                             | Free text; density / breeding pairs / recruitment / …                                                |
| manipulationMethod          | Direction of the predator manipulation                                               | Restricted; Addition / Removal / Both                                                                |
| manipulationType            | Enclosure design                                                                     | Restricted; Open area / Predator exclosure                                                           |
| locationMainlandIsland      | Location context (Australia classed as mainland, per original)                       | Restricted; Mainland / Island                                                                        |
| locationContinent           | Continent / region of the study                                                      | Restricted; Australia / Europe / N. America / … ; plus isAustralia flag                              |
| locationLatitude            | Latitude (decimal degrees)                                                           | Numeric; −33.9                                                                                       |
| predatorMeanWeight          | Mean predator body weight                                                            | Numeric (g or kg; unit recorded)                                                                     |
| preyMeanWeight              | Mean prey body weight                                                                | Numeric (g or kg; unit recorded)                                                                     |
| predatorPreyWeightRatio     | Predator/prey weight ratio                                                           | Numeric                                                                                              |
| manipulationArea            | Spatial scale of the manipulation                                                    | Numeric (ha; convert km² → ha)                                                                       |
| manipulationDuration        | Temporal scale of the manipulation                                                   | Numeric (months)                                                                                     |
| controlMean / treatmentMean | Means of control and predator-manipulated groups                                     | Numeric                                                                                              |
| controlSD / treatmentSD     | Dispersion (converted to SD if SE/CL reported; longest bar if asymmetrical)          | Numeric                                                                                              |
| controlN / treatmentN       | Number of replicates per group                                                       | Numeric                                                                                              |
| effectSizeRatio             | Treatment/control ratio X_e/X_c (unreplicated currency, retained for comparability)  | Numeric                                                                                              |
| samplingBasis               | Basis of the recorded value                                                          | Restricted; End-of-experiment / Mean-over-study / Cycle-peak                                         |
| effectSizeSourceType        | Where the value was extracted from                                                   | Restricted; Text / Table / Figure / Supplementary                                                    |
| effectSizeProvenance        | How the analysis effect size was obtained (for flagging in sensitivity analyses)     | Restricted; Directly calculated / Converted between metrics / Reconstructed from original supplement |
| descriptionStudyComplexity  | Complexity of extraction (proxy for effort/expertise)                                | Restricted; Easy / Moderate / Hard                                                                   |
| descriptionGeneralNote      | Relevant extraction notes                                                            | Free text                                                                                            |

## 3.9. Data synthesis

Analyses will be scripted in R (with `metafor`, `orchaRd`, `rotl`, `ape`) and version-controlled in this
repository; the full workflow — data, code, model objects, diagnostics, and figures — will be compiled into a
reproducible **Quarto** website with pinned package versions, as in the parallel `mate_choice_meta` update, and
archived with the data (see _Data availability_).

**For Q0 (reproduce/replicate the original):** we re-implement the original analyses on the reconstructed
dataset. (1) **Replicated experiments:** **Hedges' _d_** with the categorical homogeneity framework (total
heterogeneity _Q__T partitioned into *Q*\_M and *Q*\_E), random-effects models, 4999-iteration resampling, and
bias-corrected 95% CIs — reproducing the MetaWin v. 2.1 results, and the weighted-regression tests of *d*
against spatial/temporal scale. (2) **Unreplicated experiments:** the ratio **X_e/X_c** (ln-transformed) with
Satterthwaite \_t_-tests across study traits, reproducing the SAS results. (3) **Pooled GLM:** a
**negative-binomial GLM** (log link) of pooled population-size responses with predator origin, manipulation
type, predator class, and location plus second-order interactions and continuous covariates (weight ratio,
area, duration), with `stepAIC`/AIC_c model selection and Akaike weights, reproducing the S-Plus results. We
verify recovery of the published estimates (the _Q_\_M contrasts, the ~2× alien effect, the Australian effect,
and the GLM deviance/AIC_c tables).

**For Q1 (the update):** we move to a **single unified effect-size currency** and one **multilevel model**.

_Harmonising the effect-size currencies._ Because the original split its analysis between Hedges' _d_ (replicated)
and a raw ratio X*e/X_c (unreplicated) — the latter chosen partly to accommodate control means of zero — we will
adopt a common metric suited to the whole dataset (the **log response ratio, lnRR**, with appropriate handling of
near-zero controls, or \*\*SMD/Hedges' \_g*** where variances allow), computed with `metafor::escalc` (Borenstein et
al. 2009; Viechtbauer 2010). Following the harmonisation strategy of the parallel `mate_choice_meta` update, effect
sizes reported in one currency will be **converted** to the common metric using the standard analytic conversions
(and, where only test statistics or ratios are available, reconstructed via standard formulae), with each converted
or reconstructed value **flagged** (`effectSizeProvenance`) so it can be separated from directly calculated effects
in sensitivity analyses. This lets the replicated and unreplicated streams — analysed *separately* in the original —
be combined in one coherent model, with **study design (replicated vs. unreplicated)\*\* entering as a moderator (and,
in sensitivity analyses, as a subset filter).

_Model structure._ We will fit **multilevel `rma.mv` models** (metafor; Viechtbauer 2010) with crossed/nested random
effects for **study ID**, **effect-size (observation) ID**, **predator species** and **prey species** (each with a
non-phylogenetic and a phylogenetic component; see below), and **site/location**. Non-independence among effect sizes
that share a study or a common control (e.g. one control contrasted with several treatments, or several prey species
scored in one study) will be modelled with a **variance–covariance matrix** (assuming a within-cluster correlation
of _r_ = 0.5), and inference will use **cluster-robust (RVE/CR2) confidence intervals** (Pustejovsky & Tipton 2022).
This VCV approach **replaces the original's crude averaging** of multiple prey species to one effect per study,
retaining the within-study information while respecting the dependence. Heterogeneity will be decomposed as total and
**partial I² per random factor** (`orchaRd::i2_ml`; Nakagawa et al. 2023; Yang et al. 2025), and results visualised
with **orchard** and **bubble** plots (`orchaRd::orchard_plot`, `orchaRd::bubble_plot`).

_Moderators._ We retain the original moderators — **predator origin**, **location**, **predator class**,
**manipulation type**, **predator/prey weight ratio**, **manipulation area**, **manipulation duration** — for
comparability, and extend them where new data permit. Retaining the original specification (re-implemented for Q0)
alongside the updated one lets us attribute changes from the Q0 baseline to the new data versus the new methods.

**Phylogenetic non-independence (predators and prey).** Unlike the original — which used no phylogenetic control —
we account for shared evolutionary history among the manipulated **predator** species and among the **prey** species.
Following the workflow used in the parallel `mate_choice_meta` update (Cinar et al. 2022), we assemble a synthetic
tree for each set from the **Open Tree of Life** (via the `rotl` R package; Michonneau et al. 2016), reconcile names
to accepted binomials, resolve polytomies at random into a strictly bifurcating topology (`ape::multi2di`; Paradis &
Schliep 2019), and — as reliable branch lengths are unavailable — compute branch lengths by **Grafen's (1989)**
method. From each ultrametric tree we derive a **phylogenetic correlation matrix** included as a random effect in the
`rma.mv` models (alongside the non-phylogenetic species effect), so that per-species and phylogenetic heterogeneity
are estimated separately. Species the Open Tree cannot place will be grafted next to a congener and this noted.

**Addressing geographic generality (Q1a; Australia dominance).** Because the original alien > native signal was
driven by Australian mainland experiments, with none from non-Australian mainlands, we (1) include
**region/continent** and an explicit **Australia indicator** as moderators; (2) fit the **predator origin ×
location** and **origin × region** interactions within the multilevel model; and (3) run a **leave-Australia-out
sensitivity analysis**, reporting whether the alien-vs-native contrast persists in magnitude and significance
without the Australian studies now that more non-Australian evidence is available.

**Re-examining island vs. mainland (Q1b).** We re-test the original's second question — no greater impact on
islands than the mainland — with the enlarged dataset, explicitly separating the **island** signal from the
**Australian** signal (the original classed Australia as mainland despite its island-like biogeography). We
report the **origin × location** interaction and, as a sensitivity analysis, a three-level location factor
(non-Australian mainland / Australia / island).

**Testing the filter effect / evolutionary novelty (Q1c).** As an a-priori test of the mechanism the original
invokes but does not measure, we fit — within the alien-predator subset — a meta-regression of the effect size on
**time since the predator's establishment** at the study region (`timeSinceEstablishment`). The filter effect
predicts a **negative slope** (suppression weakening as naive prey are filtered out); we report the slope, its
cluster-robust CI, and the share of heterogeneity it explains, and visualise it with a bubble plot. Because
establishment dates are expected to be sparsely and unevenly reported, we will (i) state the number and proportion
of alien-predator effect sizes for which a date could be obtained, (ii) treat the test as **exploratory** if
coverage is low, and (iii) not impute missing dates. This analysis operationalises the interpretation of the
origin contrast (Q1a) as an evolutionary-novelty gradient.

**Comparing original vs. updated estimates.** Following Pollo et al. (2025), we will compare the original and
updated estimates both **qualitatively** (sign/significance class: alien effect greater / not different / prey
suppressed or not, by 95% CI overlap) and **quantitatively** (an absolute difference between estimates yielding
a z-score > 1.96; two-tailed α = 0.05). The reproduction (Q0) estimates anchor this comparison. Because the
effect-size currency changes between Q0 and Q1, comparisons will be made on standardized scales and, where
necessary, by re-fitting the updated model in the original currency for a like-for-like contrast.

**Sensitivity and influence analyses.** We will test the robustness of the updated pooled estimates with, at
minimum: (1) **leave-one-study-out** and **leave-one-species-out** re-fits (recomputing the VCV matrix and
subsetting the phylogenetic correlation matrix each time; `orchaRd::leave_one_out` / `orchard_leave1out`); (2) the
**leave-Australia-out** analysis (Q1a); (3) **directly calculated vs. converted/reconstructed** effect sizes (using
the `effectSizeProvenance` flag), to confirm metric conversions do not drive the result; (4) **new evidence vs.
reconstructed-original** subsets, to see whether the update's conclusions rest on the new data or the original;
(5) removal of statistical **outliers** (|standardized residual| > 3); and (6) re-fitting with **range-shifter and
human-subsidised "native" predators** (the `predatorOriginFlag` cases) reclassified or excluded, to confirm the
origin contrast is not an artefact of ambiguous-origin coding. We will report the largest shift in any pooled mean
across these analyses.

## 3.10. Publication / dissemination bias

The original assessed bias only for the replicated subset (normal quantile plot; Wang & Bushman 1998). Applying
current practice (Nakagawa et al. 2022) to the **whole** updated dataset, we will assess bias by: (1) a **multilevel
Egger's regression** — a two-step approach following the parallel `mate_choice_meta` update: we first include the SE
(√variance) of effect sizes as a moderator (intercept ≠ 0 at P ≤ 0.05 flags small-study effects) and, if the slope
is significant, **re-fit with the sampling variance as the moderator** to read off a less-biased adjusted mean; (2)
a **funnel plot** of model residuals against precision; (3) a **time-lag bias** check including publication year
(and an original-vs-new evidence indicator) as moderators; and (4) inspection of **outliers** (|standardized
residual| > 3) with sensitivity analyses removing them. In addition, we will estimate the **bias-corrected overall
mean under two complementary frameworks** and compare them directly: the Nakagawa et al. (2022) sampling-variance
intercept method (the mean at zero sampling error), and the **bias-robust** estimator of Yang et al. (2023) (a fixed/common-
effects GLS weighting less susceptible to selective reporting, combined with cluster-robust CR2 variances), overlaid
on an orchard plot (`orchaRd::pub_bias_plot`). We will also report the normal quantile plot for continuity with the
original.

---

# 4. References

- Banks, P. B., & Dickman, C. R. (2007). Alien predation and the effects of multiple levels of prey naiveté.
  _Trends in Ecology & Evolution_ 22(5):229–230. https://doi.org/10.1016/j.tree.2007.02.006
- Blackburn, T. M., Cassey, P., Duncan, R. P., Evans, K. L., & Gaston, K. J. (2004). Avian extinction and
  mammalian introductions on oceanic islands. _Science_ 305:1955–1958. https://doi.org/10.1126/science.1101617
- Borenstein, M., Hedges, L. V., Higgins, J. P. T., & Rothstein, H. R. (2009). _Introduction to
  Meta-Analysis._ Wiley-Blackwell.
- Burnham, K. P., & Anderson, D. R. (2000). _Model Selection and Inference: A Practical Information-Theoretic
  Approach._ Springer.
- Carthey, A. J. R., & Banks, P. B. (2014). Naïveté in novel ecological interactions: lessons from theory and
  experimental evidence. _Biological Reviews_ 89(4):932–949. https://doi.org/10.1111/brv.12087
- Cinar, O., Nakagawa, S., & Viechtbauer, W. (2022). Phylogenetic multilevel meta-analysis: A simulation study on
  the importance of modelling the phylogeny. _Methods in Ecology and Evolution_ 13(2):383–395.
  https://doi.org/10.1111/2041-210X.13760
- Colautti, R. I., Ricciardi, A., Grigorovich, I. A., & MacIsaac, H. J. (2004). Is invasion success explained by
  the enemy release hypothesis? _Ecology Letters_ 7(8):721–733. https://doi.org/10.1111/j.1461-0248.2004.00616.x
- Côté, I. M., & Sutherland, W. J. (1997). The effectiveness of removing predators to protect bird
  populations. _Conservation Biology_ 11:395–405. https://doi.org/10.1046/j.1523-1739.1997.95410.x
- Courchamp, F., Langlais, M., & Sugihara, G. (2000). Rabbits killing birds: modelling the hyperpredation
  process. _Journal of Animal Ecology_ 69(1):154–164. https://doi.org/10.1046/j.1365-2656.2000.00383.x
- Cox, J. G., & Lima, S. L. (2006). Naiveté and an aquatic–terrestrial dichotomy in the effects of introduced
  predators. _Trends in Ecology & Evolution_ 21:674–680. https://doi.org/10.1016/j.tree.2006.07.011
- Doherty, T. S., Glen, A. S., Nimmo, D. G., Ritchie, E. G., & Dickman, C. R. (2016). Invasive predators and
  global biodiversity loss. _Proceedings of the National Academy of Sciences USA_ 113(40):11261–11265.
  https://doi.org/10.1073/pnas.1602480113
- Egger, M., Davey Smith, G., Schneider, M., & Minder, C. (1997). Bias in meta-analysis detected by a simple,
  graphical test. _BMJ_ 315:629–634. https://doi.org/10.1136/bmj.315.7109.629
- Errington, P. L. (1956). Factors limiting higher vertebrate populations. _Science_ 124:304–307.
  https://doi.org/10.1126/science.124.3216.304
- Foo, Y. Z., O'Dea, R. E., Koricheva, J., Nakagawa, S., & Lagisz, M. (2021). A practical guide to question
  formation, systematic searching and study screening for literature reviews in ecology and evolution.
  _Methods in Ecology and Evolution_ 12(9):1705–1720. https://doi.org/10.1111/2041-210X.13654
- Grafen, A. (1989). The phylogenetic regression. _Philosophical Transactions of the Royal Society B_
  326(1233):119–157. https://doi.org/10.1098/rstb.1989.0106
- Gurevitch, J., & Padilla, D. K. (2004). Are invasive species a major cause of extinctions? _Trends in Ecology
  & Evolution_ 19:470–474. https://doi.org/10.1016/j.tree.2004.07.005
- Gurevitch, J., Morrison, J. A., & Hedges, L. V. (2000). The interaction between competition and predation: a
  meta-analysis of field experiments. _American Naturalist_ 155:435–453. https://doi.org/10.1086/303337
- Harzing, A. W. (2007). _Publish or Perish._ Software. https://harzing.com/resources/publish-or-perish
- Hedges, L. V., Gurevitch, J., & Curtis, P. S. (1999). The meta-analysis of response ratios in experimental
  ecology. _Ecology_ 80:1150–1156. https://doi.org/10.2307/177062
- Koricheva, J., Gurevitch, J., & Mengersen, K. (eds.) (2013). _Handbook of Meta-Analysis in Ecology and
  Evolution._ Princeton University Press.
- Korpimäki, E., & Krebs, C. J. (1996). Predation and population cycles of small mammals. _BioScience_
  46:754–764. https://doi.org/10.2307/1312851
- Lagisz, M., Yang, Y., Young, S., & Nakagawa, S. (2025). A practical guide to evaluating sensitivity of
  literature search strings for systematic reviews using relative recall. _Research Synthesis Methods_
  16(1):1–14. https://doi.org/10.1017/rsm.2024.6
- Letnic, M., Ritchie, E. G., & Dickman, C. R. (2012). Top predators as biodiversity regulators: the dingo
  _Canis lupus dingo_ as a case study. _Biological Reviews_ 87(2):390–413.
  https://doi.org/10.1111/j.1469-185X.2011.00203.x
- Long, J. L. (2003). _Introduced Mammals of the World._ CSIRO Publishing.
- Michonneau, F., Brown, J. W., & Winter, D. J. (2016). rotl: an R package to interact with the Open Tree of Life
  data. _Methods in Ecology and Evolution_ 7(12):1476–1481. https://doi.org/10.1111/2041-210X.12593
- Moher, D., Liberati, A., Tetzlaff, J., Altman, D. G., & PRISMA Group (2009). Preferred reporting items for
  systematic reviews and meta-analyses: the PRISMA statement. _PLoS Medicine_ 6:e1000097.
  https://doi.org/10.1371/journal.pmed.1000097
- Nakagawa, S., & Parker, T. H. (2015). Replicating research in ecology and evolution: feasibility, incentives,
  and the cost–benefit conundrum. _BMC Biology_ 13(1):88. https://doi.org/10.1186/s12915-015-0196-3
- Nakagawa, S., Lagisz, M., Jennions, M. D., Koricheva, J., Noble, D. W. A., Parker, T. H., Sánchez-Tójar, A.,
  Yang, Y., & O'Dea, R. E. (2022). Methods for testing publication bias in ecological and evolutionary
  meta-analyses. _Methods in Ecology and Evolution_ 13(1):4–21. https://doi.org/10.1111/2041-210X.13724
- Nakagawa, S., Lagisz, M., O'Dea, R. E., Pottier, P., Rutkowska, J., Senior, A. M., Yang, Y., & Noble, D. W. A.
  (2023). orchaRd 2.0: An R package for visualising meta-analyses and heterogeneity. _Methods in Ecology and
  Evolution_ 14(8):2003–2010. https://doi.org/10.1111/2041-210X.14152
- Newton, I. (1998). _Population Limitation in Birds._ Academic Press.
- O'Dea, R. E., Lagisz, M., Jennions, M. D., Koricheva, J., Noble, D. W. A., Parker, T. H., Gurevitch, J.,
  Page, M. J., Stewart, G., Moher, D., & Nakagawa, S. (2021). Preferred reporting items for systematic reviews and
  meta-analyses in ecology and evolutionary biology: a PRISMA extension. _Biological Reviews_ 96(5):1695–1722.
  https://doi.org/10.1111/brv.12721
- Ouzzani, M., Hammady, H., Fedorowicz, Z., & Elmagarmid, A. (2016). Rayyan — a web and mobile app for
  systematic reviews. _Systematic Reviews_ 5(1):210. https://doi.org/10.1186/s13643-016-0384-4
- Pick, J. L., Nakagawa, S., & Noble, D. W. A. (2019). Reproducible, flexible and high-throughput data
  extraction from primary literature: the metaDigitise R package. _Methods in Ecology and Evolution_
  10(3):426–431. https://doi.org/10.1111/2041-210X.13118
- Paradis, E., & Schliep, K. (2019). ape 5.0: an environment for modern phylogenetics and evolutionary analyses in
  R. _Bioinformatics_ 35(3):526–528. https://doi.org/10.1093/bioinformatics/bty633
- Pimm, S. L., Moulton, M. P., & Justice, L. J. (1995). Bird extinctions in the central Pacific. In _Extinction
  Rates_ (eds J. H. Lawton & R. M. May), pp. 75–87. Oxford University Press.
- Pollo, P., Lagisz, M., Macedo-Rego, R. C., Mizuno, A., Yang, Y., & Nakagawa, S. (2025). Reliability of
  meta-analyses in ecology and evolution: (mostly) good news from a case study on sexual signals. _Proceedings
  of the Royal Society B_ 292(2047):20242782. https://doi.org/10.1098/rspb.2024.2782
- Prugh, L. R., Stoner, C. J., Epps, C. W., Bean, W. T., Ripple, W. J., Laliberte, A. S., & Brashares, J. S.
  (2009). The rise of the mesopredator. _BioScience_ 59(9):779–791. https://doi.org/10.1525/bio.2009.59.9.9
- Pustejovsky, J. E., & Tipton, E. (2022). Meta-analysis with robust variance estimation: Expanding the range of
  working models. _Prevention Science_ 23(3):425–438. https://doi.org/10.1007/s11121-021-01246-3
- Richardson, W. S., Wilson, M. C., Nishikawa, J., & Hayward, R. S. A. (1995). The well-built clinical
  question: a key to evidence-based decisions. _ACP Journal Club_ 123(3):A12.
  https://doi.org/10.7326/ACPJC-1995-123-3-A12
- Ritchie, E. G., & Johnson, C. N. (2009). Predator interactions, mesopredator release and biodiversity
  conservation. _Ecology Letters_ 12(9):982–998. https://doi.org/10.1111/j.1461-0248.2009.01347.x
- Rosenberg, M. S., Adams, D. C., & Gurevitch, J. (2000). _MetaWin: Statistical Software for Meta-Analysis.
  Version 2._ Sinauer Associates.
- Rosenthal, R. (1979). The "file drawer problem" and tolerance for null results. _Psychological Bulletin_
  86:638–641. https://doi.org/10.1037/0033-2909.86.3.638
- Sánchez-Tójar, A., Nakagawa, S., Sánchez-Fortún, M., Martin, D. A., Ramani, S., Girndt, A., Bókony, V., Kempenaers,
  B., Liker, A., Westneat, D. F., Burke, T., & Schroeder, J. (2018). Meta-analysis challenges a textbook example of
  status signalling and demonstrates publication bias. _eLife_ 7:e37385. https://doi.org/10.7554/eLife.37385
- Salo, P., Korpimäki, E., Banks, P. B., Nordström, M., & Dickman, C. R. (2007). Alien predators are more
  dangerous than native predators to prey populations. _Proceedings of the Royal Society B_ 274:1237–1243.
  https://doi.org/10.1098/rspb.2006.0444
- Salo, P., Banks, P. B., Dickman, C. R., & Korpimäki, E. (2010). Predator manipulation experiments: impacts on
  populations of terrestrial vertebrate prey. _Ecological Monographs_ 80(4):531–546. https://doi.org/10.1890/09-1260.1
- Sih, A., Bolnick, D. I., Luttbeg, B., Orrock, J. L., Peacor, S. D., Pintor, L. M., Preisser, E., Rehage, J. S.,
  & Vonesh, J. R. (2010). Predator–prey naïveté, antipredator behavior, and the ecology of predator invasions.
  _Oikos_ 119(4):610–621. https://doi.org/10.1111/j.1600-0706.2009.18039.x
- Sinclair, A. R. E., Pech, R. P., Dickman, C. R., Hik, D., Mahon, P., & Newsome, A. E. (1998). Predicting
  effects of predation on conservation of endangered prey. _Conservation Biology_ 12:564–575.
  https://doi.org/10.1046/j.1523-1739.1998.97030.x
- Viechtbauer, W. (2010). Conducting meta-analyses in R with the metafor package. _Journal of Statistical
  Software_ 36(3):1–48. https://doi.org/10.18637/jss.v036.i03
- Viechtbauer, W., & Cheung, M. W.-L. (2010). Outlier and influence diagnostics for meta-analysis. _Research
  Synthesis Methods_ 1:112–125. https://doi.org/10.1002/jrsm.11
- Wang, M. C., & Bushman, B. J. (1998). Using the normal quantile plot to explore meta-analytic data sets.
  _Psychological Methods_ 3:46–54. https://doi.org/10.1037/1082-989X.3.1.46
- Yang, Y., Sánchez-Tójar, A., O'Dea, R. E., Noble, D. W. A., Koricheva, J., Jennions, M. D., Parker, T. H.,
  Lagisz, M., & Nakagawa, S. (2023). Publication bias impacts on effect size, statistical power, and magnitude
  (Type M) and sign (Type S) errors in ecology and evolutionary biology. _BMC Biology_ 21:71.
  https://doi.org/10.1186/s12915-022-01485-y
- Yang, Y., Noble, D. W. A., Spake, R., Senior, A. M., Lagisz, M., & Nakagawa, S. (2025). A pluralistic
  framework for measuring, interpreting and decomposing heterogeneity in meta-analysis. _Methods in Ecology and
  Evolution_ 16(11):2710–2725. https://doi.org/10.1111/2041-210x.70155

> _Additional primary studies (benchmark set, included studies) will be added as the search and screening
> proceed._
