# Summary of the meta-analysis to be updated

**Source paper:** Salo, P., Korpimäki, E., Banks, P. B., Nordström, M., & Dickman, C. R. (2007).
*Alien predators are more dangerous than native predators to prey populations.* **Proceedings of the
Royal Society B** 274:1237–1243. doi:10.1098/rspb.2006.0444 (received 22 Dec 2006; accepted 9 Feb 2007;
published online 13 March 2007).

This document summarizes the original study. It is the starting point for the protocol of the planned
**update** of this meta-analysis.

---

## 1. Background and rationale

- Alien predators are considered one of the most important causes of declines and extinctions of species
  and of biodiversity loss worldwide, with especially destructive effects reported for insular ecosystems.
  Prey in such systems are often naive to the hunting tactics of novel predators.
- A traditional paradigm (Errington 1956) held that *native* vertebrate predators do **not** have
  detrimental effects on prey population sizes, because coexisting predators take mainly non-reproductive
  or "doomed" surplus individuals (compensatory mortality).
- Over the ~20 years before the study this view shifted: native predators can limit or even regulate prey
  population sizes (e.g. Korpimäki & Krebs 1996; Côté & Sutherland 1997; Sinclair et al. 1998; Gurevitch
  et al. 2000; Korpimäki et al. 2004) and occasionally locally obliterate them (Kavanagh 1988).
- Nonetheless the **prevailing dogma** remained that alien predators have far more detrimental effects on
  the population sizes and diversity of native animals than do native predators (Wood Jones 1925;
  Troughton 1941; Diamond 1989; Blackburn et al. 2004) — an assertion underlying great conservation
  concern but **not previously critically evaluated** (Gurevitch & Padilla 2004).
- The study therefore performed a worldwide search of field experiments in which the population densities
  of vertebrate (mammalian and avian) predators had been manipulated, and meta-analysed the responses of
  their vertebrate prey. Focus was on **direct impacts on prey population size and reproduction**, which
  have the most immediate consequences for conservation.

### Terminology / conventions used in the paper
- **Alien / introduced predator:** a predator considered introduced (versus native) based on definitions
  provided in each study, confirmed using Long (2003).
- **Predator addition:** release of predators into experimental areas or attraction of predators (e.g.
  attracting raptors with perch sites).
- **Predator removal:** exclosure experiments or manipulations where predators were killed or relocated.
- **Prey responses:** classified as either **population size** (density, minimum number known alive,
  breeding pairs, rate of increase/survival, catch-per-unit-effort) or **reproductive** (numbers of
  juveniles/broods, females with young, survival of young, mean recruitment). *Per capita* measures (e.g.
  brood size, fledglings per pair) were **not** used.
- **Sign convention (Hedges' *d*):** **positive *d*** = predator treatment had a positive effect on the
  prey species; **zero** = no difference between treatment and control; **negative *d*** = greater
  response in the controls (i.e. predators suppressed prey).

## 2. Objectives

Two main questions:
1. Do **alien predators** impact vertebrate prey **more than native predators** (on prey population size
   and reproduction)?
2. Are the impacts of predation **more intense in insular than mainland** ecosystems?

## 3. Data sources and scope

- **Literature search:** online databases **Web of Science, Biosis Previews, and Biological Abstracts**,
  using combinations of the keywords: *introduced; alien; feral; predator; predation; experiment;
  manipulation; removal; reduction; control; effect; impact*. Bibliographies of earlier reviews (Côté &
  Sutherland 1997; Newton 1998) and of retrieved papers were also used. **Data searches ended January
  2006.**
- **Screening:** a preliminary search yielded **159 articles**, of which **84 were discarded** (did not
  meet criteria), leaving **45 replicated studies** and **30 unreplicated studies** (30 studies describing
  35 experiments). Sources included international ecology/conservation/wildlife journals, book chapters,
  and one unpublished Ph.D. thesis; articles were published **1939–2006**, most from the last 10 years.
- **Two datasets:**
  - **Replicated experiments (n = 45):** ≥2 control and ≥2 treatment plots, or a before-and-after design.
    Analysed with formal meta-analysis (Hedges' *d*).
  - **Unreplicated experiments (n = 35 rows):** only one sample for treatment and/or control; analysed
    with ratio-based and regression approaches (cannot use conventional meta-analysis).
- **Effect size (replicated):** **Hedges' *d*** computed in **MetaWin v. 2.1** (Rosenberg et al. 2000).
  Hedges' *d* was chosen over the log response ratio (ln*R*) because the data were unsuitable for a
  response ratio (control group value = zero in some studies; Hedges et al. 1999).
- **Effect size (unreplicated):** the ratio **X_e / X_c** (treatment mean / control mean). A ratio > 1
  means the manipulation had a positive effect on prey; a ratio ≤ 1 means no effect or a negative effect.
- **Data availability:** primary data are contained in the **electronic supplementary material**
  (Appendix S1; table S1 = 45 replicated experiments; table S2 = 35 unreplicated rows). **No open data
  repository or analysis code was published** — a key consideration for the reproduction step of the
  update (see §8).

### Inclusion / selection criteria (abridged)
1. Publications describing the effect of **reduction or addition of avian or mammalian predators** on
   **avian or mammalian prey** (excluding livestock and other non-native prey).
2. Studies removing **both** native and introduced predators were **excluded** if the effects of the two
   predator groups could not be separated.
3. Acceptable prey responses classified as **population size** or **reproductive** (see terminology).
4. Studies must have run long enough (**≥ 1 prey generation**) for a demographic prey response; studies
   measuring other parameters or using other units were omitted.
5. Necessary data — **sample sizes, means of controls and treatments, and a measure of variability
   (SD/SE/CL)** — extracted from text, tables, or figures. Asymmetrical error bars → variances computed
   conservatively from the longest bars; if no variances given, computed from raw results. End-of-experiment
   data used where possible; otherwise an arithmetic mean over the study. Cyclically fluctuating species →
   data from the **peak phase** of the cycle. Reproductive responses taken separately per year, then
   averaged to one effect size per study. Authors were contacted for missing data.

### Coded study traits (moderators)
Type of prey (rodent, ungulate, marsupial, …); prey class (bird / mammal); **origin of predator
(native / introduced)**; predator class (bird / mammal / both); **method of manipulation
(addition / removal)**; **location (mainland / island)**; habitat; spatial and temporal scale
(**manipulation area** and **manipulation duration**); continent; and **manipulation type (open terrain
vs. predator exclosure)**. Mean prey and predator weights gave a **predator/prey weight ratio**. Data
collection was performed by two persons (M.N. and P.S.).

## 4. Statistical methods

- **Replicated experiments — categorical meta-analysis** (MetaWin v. 2.1): homogeneity statistic **Q**,
  total heterogeneity *Q*_T partitioned into *Q*_M (explained by the model) and *Q*_E (residual);
  **random-effects models**; **resampling tests with 4999 iterations**; **bias-corrected 95% CIs**;
  significance evaluated at 0.05; all tests two-tailed. A **continuous** (weighted linear regression)
  analysis tested whether *d* was affected by spatial or temporal scale.
- **Publication bias (replicated only):** assessed with the **normal quantile plot** method (Wang &
  Bushman 1998) — no evidence of bias found. Not possible for the unreplicated studies; the file-drawer
  problem was argued to be unlikely given the expense of predator-manipulation experiments (Rosenthal
  1979).
- **Unreplicated experiments:** effect size = X_e / X_c (ln-transformed for normality); differences in
  effect size across study traits tested with **Student's *t*-test with the Satterthwaite option for
  heteroscedastic variances** (SAS v. 9.1).
- **Pooled generalized linear model** (to analyse multiple factors and interactions simultaneously, which
  neither MetaWin nor the *t*-tests allow): population-size responses of replicated (*n* = 32) and
  unreplicated (*n* = 28) experiments pooled, using X_e / X_c as the effect measure. A **negative-binomial
  GLM** (`glm.nb`, MASS library, S-Plus v. 6) with a **log link**. Main explanatory variables: **predator
  origin** (native/alien), **manipulation type** (open vs. exclosure), **predator class** (mammal/bird/both),
  and **location** (mainland/island), with second-order interactions; **predator/prey weight ratio**,
  **manipulation area**, and **manipulation duration** as continuous covariates. Australia was classified
  as mainland. Model selection by stepwise AIC (`stepAIC`, MASS) using **AIC_c** (small-sample corrected);
  support judged by AIC_c differences (Δ_i ≤ 2 = substantial support) and **Akaike weights** *w_i*
  (Burnham & Anderson 2000). Some interactions were dropped owing to singularities (empty cells).

## 5. Key results

- **Composition of the replicated dataset (n = 45):** predators manipulated were native in **37 studies
  (82%)** and introduced in **8**; predatory mammals (24 studies), mammals + birds combined (17), only
  4 on predatory birds alone. Prey were mammals in 27 studies (mostly small rodents, 23) and birds in 18
  (waterfowl the most-studied group, 10). Most manipulations (41) were **removals/reductions**; 3
  additions; 1 both. Experiments lasted 2.5 months–9 years (median 25 months); areas 0.13 ha–77.5 km²
  (median 2.2 km²).
- **Alien > native (replicated):** the effect of introduced predators on prey was more than **double** that
  of native predators (figure 1a; *Q*_M = 4.96, d.f. = 1, *p* = 0.020).
- **Australian effect:** prey responses to removal of introduced predators **in Australia** (all
  mammalian) were **twofold** higher than to introduced predators elsewhere and **threefold** higher than
  to native predators generally (figure 1b; *Q*_M = 7.07, d.f. = 2, *p* = 0.022).
- **Response type:** reproductive effects were significantly larger than population-size effects (table 1);
  re-analysing **only population-size** experiments still gave a significant alien-vs-native difference
  (*Q*_M = 9.54, d.f. = 1, *p* = 0.001).
- **Exclosure ("fence") effect:** effect sizes in exclosure vs. open-terrain experiments were similar;
  removing exclosure experiments actually **increased** the alien–native difference. No bias from study
  duration (slope 0.017, *p* = 0.99) or spatial coverage (slope 0.001, *p* = 0.51).
- **Unreplicated (n = 35):** results closely mirrored the replicated set — introduced predators had on
  average **~2.5 times** higher effect than native predators (figure 2a; *t* = 2.22, d.f. = 16.3,
  *p* = 0.041), again driven largely by Australian studies. Population-size and reproductive responses did
  not differ (*t* = 1.18, *p* = 0.258). No biases from duration or spatial coverage.
- **Pooled GLM (replicated + unreplicated, 60 experiments):** stepwise AIC_c favoured models containing
  **predator origin**, **location**, and their **interaction**. Analysis of deviance: **predator origin**
  had a **highly significant** effect on prey population responses (deviance = 52.63, residual d.f. = 58,
  *p* < 0.0001); the **origin × location** interaction was **slightly significant** (deviance = 3.90,
  *p* = 0.048); **location alone** was not (deviance = 2.16, *p* = 0.14). Median effect (X_e/X_c) for
  introduced mainland predators = **14.79** vs. **1.41** for native mainland (table 2b).

## 6. Main conclusions

- Analysing **80 published experimental manipulations** of predator density, the study provided the
  **first explicit quantitative support** for the prevailing dogma that **alien predators impose more
  severe impacts on prey populations than do native predators**.
- Alien predators can hold prey populations **further below their predator-free densities** than native
  predators do, making prey more vulnerable to stochastic extinction — contradicting the idea that alien
  predators merely *compensate* for lost native predators.
- **No support** was found for the expectation of greater alien-predator impacts on **islands** than on
  the **mainland**; the authors attribute this partly to Australia's **island-like** characteristics
  (geographical isolation, endemic fauna, prey now restricted to habitat refugia).
- The pattern is interpreted through **prey naiveté** and the **"filter effect"** (Pimm et al. 1995):
  species surviving the initial invasion may be relatively resistant to ongoing impacts.

## 7. Notable limitations (relevant to the update)

- **Australia dominates the alien-predator signal.** Few experiments on alien predators exist from other
  regions and **none from mainland situations outside Australia**; the large overall alien effect is
  driven mainly by consistently high Australian effect sizes (the authors state this explicitly).
- **Two incompatible effect-size currencies.** Replicated studies used Hedges' *d*; unreplicated studies
  used a raw ratio X_e/X_c; the pooled analysis used a negative-binomial GLM on the ratio. This
  patchwork complicates interpretation and modern re-analysis.
- **Publication bias** was checked only for the replicated set (normal quantile plot) and not for the
  unreplicated set.
- **Taxonomic/geographic imbalance:** heavy representation of small rodents and waterfowl; predator
  manipulations dominated by native predators (82% of replicated studies) and by removals over additions.
- **No open data or code:** primary data reside only in the electronic supplementary material (tables S1,
  S2); analyses were run in three different proprietary packages (MetaWin, SAS, S-Plus).
- **Search vintage:** conducted up to January 2006 — nearly two decades of subsequent primary literature
  (including many more mainland non-Australian alien-predator manipulations) are not included.
- **Search scope:** three abstracting databases and English-language Boolean terms only.

## 8. Opportunities for the update (to be refined in the formal protocol)

The planned update follows a **reproduce/replicate-then-update** design with two research questions (see
[`02_update_protocol.md`](02_update_protocol.md)): **Q0** reconstructs the original dataset from the
electronic supplementary material and re-implements the original analyses to recover the published
estimates; **Q1** then updates the synthesis by combining new sources, new data, and updated methods in a
single integrated step.

- **Reconstruct-then-reproduce first (Q0):** because there is **no archived dataset or code**, digitise
  tables S1/S2 from the supplementary material, re-implement the MetaWin/SAS/S-Plus analyses in R, and
  verify that the published estimates (e.g. *Q*_M values, the alien > native contrast, the Australian
  effect) are recovered. This provides the baseline for all comparisons.
- **Validate the reconstruction:** independently re-extract a **~10% sample** of the studies in tables
  S1/S2 from their original source articles to quantify any transcription/extraction drift.
- **Unify the effect-size framework:** replace the split Hedges'-*d* (replicated) / raw-ratio
  (unreplicated) approach with a single modern currency — e.g. the **log response ratio (lnRR)** or SMD
  within a **multilevel `metafor::rma.mv`** model — analysing replicated and unreplicated studies together
  with **study design (replicated vs. unreplicated) as a moderator** and appropriate handling of the
  "control = zero" cases that motivated the original choice of *d*.
- **Confront the Australia-dominance issue directly:** treat **region/continent (and an Australia flag)**
  as an explicit moderator and run sensitivity analyses excluding Australian studies, to test whether the
  alien > native conclusion holds beyond Australia now that more non-Australian evidence exists.
- **Extend coverage** well beyond the January 2006 search (~20 years of new predator-manipulation
  experiments, including more mainland non-Australian alien-predator studies).
- **Broaden information sources** (add Scopus and supplementary sources; consider non-English literature)
  and reduce reliance on English-only Boolean terms.
- **Apply updated analytical methods:** multilevel models with a **taxonomic/phylogenetic random effect**
  across predator (and prey) species, **robust variance estimation**, and modern heterogeneity
  decomposition; retain the original moderator set (predator origin, location, predator class,
  manipulation type, predator/prey weight ratio, area, duration) for comparability.
- **Re-test the island vs. mainland question** with more and better-distributed data, disentangling the
  island signal from the Australian signal that confounded the original.
- **Update publication-bias diagnostics** (Egger's regression within the multilevel model, funnel plots,
  time-lag bias with publication year and an original-vs-new-evidence indicator), applied to the whole
  dataset rather than the replicated subset only.
- Re-examine whether the headline conclusions (alien > native; no island effect; reproductive > population
  responses) hold with ~20 additional years of data, and explore contemporary moderators where data permit.
