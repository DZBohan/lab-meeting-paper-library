# Gene mutant dosage in 60,000 clinical cancer samples (INCOMMON)

## Citation

Calonaci N, Krasniqi E, Colic D, et al. Gene mutant dosage is associated with prognosis and metastatic tropism in 60,000 clinical cancer samples. *Nature Genetics*. 2026;58(8):1906–1917. <https://doi.org/10.1038/s41588-026-02666-z>

- Lead contact: Giulio Caravagna (University of Trieste)
- Publisher: [Nature Genetics](https://www.nature.com/articles/s41588-026-02666-z) (open access, CC BY 4.0)
- Source code/data: [INCOMMON R package](https://caravagnalab.github.io/INCOMMON); MSK-MET via cBioPortal (`msk_met_2021`); AACR GENIE-DFCI v13.0 via Synapse
- Added to library: 2026-09-29

## Why this paper

Clinical panels report a mutation as present or absent, but the same mutation can sit on one of two alleles or on every copy of an amplified locus. This paper asks whether the number of mutant copies relative to all copies of the gene — gene mutant dosage (GMD) — carries prognostic and metastatic information that the binary mutant/wild-type call misses, and whether it can be inferred from tumor-only targeted sequencing.

## Study at a glance

- Study design: retrospective, cross-sectional analysis of clinical targeted-panel cohorts; method trained and cross-validated on whole-genome data.
- Cohort or sample size: >60,000 samples, >500,000 mutations; 21,937 MSK-MET tumors with survival data; 21,462 primary + 12,049 metastatic GENIE-DFCI samples for validation of enrichment.
- Data modality: variant and total read counts from tumor-only panels, pathology purity; priors from PCAWG + Hartwig WGS.
- Main methods: INCOMMON, a Bayesian model with Poisson depth (λ = 2η(1−π) + πηk) and binomial variant reads (φ = mπ / (2(1−π) + kπ)); empirical priors on (k, m), Beta prior on purity, Gamma prior on reads per copy; MCMC. GMD summarized as the posterior expected fraction of alleles with the mutation, E[m/k], and binned into low / balanced / high classes. Downstream: Kaplan–Meier and multivariable Cox models, Fisher tests on primary vs metastasis, logistic regression for metastatic propensity, multinomial regression for organotropism, Benjamini–Hochberg FDR per tumor type.

## Main conclusion

High GMD (loss of the wild-type allele or gain of the mutant allele) was an independent adverse prognostic factor for dozens of gene–tumor-type pairs, most consistently in the RAS/RAF pathway (for example, KRAS in pancreatic cancer, HR 3.19 vs wild type), and was enriched in metastases and associated with specific organotropic routes; 13 of 46 survival biomarkers were invisible to the binary mutant/wild-type model.

## Figure-level discussion

### Figure 1 — the INCOMMON model

- What is being measured? Total copy number k and mutation multiplicity m per mutation, plus sample purity π and reads per copy η.
- What statistical comparison is shown? Linear depth–copy-number relation in WGS (b); cross-validated error on PCAWG/Hartwig ground truth (e).
- What conclusion is supported? m is recovered well (96% within ±1 copy); k less well (79%).
- What alternative interpretation remains? Validation is on WGS read counts, not on the deep, capture-biased depth of targeted panels the method is applied to.

### Figures 2–3 — survival

- What is being measured? Overall survival by GMD class vs wild type, per gene and tumor subtype.
- What statistical comparison is shown? Log-rank tests; multivariable Cox models adjusted for age, sex, TMB, FGA and sample type; pairwise high vs balanced Wald tests.
- What conclusion is supported? High GMD tends to carry the worst prognosis, often beyond the binary mutant call.
- What alternative interpretation remains? GMD class cutoffs were tuned against the same survival outcome; purity (which drives both GMD inference and outcome) is not a covariate; FDR threshold is 0.1.

### Figures 4–5 — metastasis

- What is being measured? GMD class frequencies in primary vs metastatic samples; odds of metastasis and of specific metastatic sites.
- What statistical comparison is shown? Fisher tests with standardized residuals; logistic and multinomial regression.
- What conclusion is supported? High GMD is enriched in metastases and linked to site-specific spread.
- What alternative interpretation remains? Samples are unpaired and cross-sectional; copy-number evolution after dissemination can create the enrichment rather than predict it.

## Strengths

- Works from read counts alone, without matched normals or raw BAM files, so it scales to large clinical cohorts.
- Uncertainty is propagated: GMD is a posterior expectation rather than a hard call.
- Survival, metastatic enrichment and organotropism analyses run on the same framework, with external replication of the enrichment result in GENIE-DFCI.

## Limitations

- Assumes all mutations and copy-number states are clonal.
- A single per-copy read rate η per sample ignores locus-specific capture efficiency in targeted panels.
- Survival associations are retrospective and correlational; no survival validation cohort.

## Questions for discussion

- How much of the "high GMD" signal is general genomic instability rather than gene-specific dosage, given that FGA only partly captures it?
- Would pre-registering fixed biological cutoffs (for example m/k = 1 for LOH) change the list of significant biomarkers?
- Can GMD inferred from a metastasis sample be interpreted as a property of the primary tumor when predicting metastasis?

## Meeting notes

- Presenter:
- Meeting date:
- Key points raised:
- Follow-up papers or analyses:
