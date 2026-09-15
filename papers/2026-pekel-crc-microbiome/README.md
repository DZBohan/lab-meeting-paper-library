# Universal colorectal cancer microbiome signatures

## Citation

Pekel S, Karcher N, Essex M, et al. Meta-analysis reveals microbiome signatures for colorectal cancer that are universal across age groups and sequencing methods. *Cell Host & Microbe*. 2026;34(7):1462–1476.e5. <https://doi.org/10.1016/j.chom.2026.05.030>

- Lead contact: Georg Zeller
- PMID: [42341762](https://pubmed.ncbi.nlm.nih.gov/42341762/)
- Publisher: [Cell Host & Microbe](https://www.cell.com/cell-host-microbe/fulltext/S1931-3128(26)00223-4)
- Source code: [zellerlab/crc-meta-ii](https://github.com/zellerlab/crc-meta-ii)
- Added to library: 2026-09-15

## Why this paper

This study asks whether colorectal cancer has a reproducible gut microbial signature across cohorts, sequencing technologies, and age at disease onset. It is particularly useful for discussing whether early-onset CRC (EO-CRC) represents a microbiologically distinct disease from late-onset CRC (LO-CRC).

## Study at a glance

- Meta-analysis of 6,779 fecal microbiome samples from 27 studies.
- Uniformly reprocessed 1,948 whole-genome shotgun and 4,831 16S rRNA profiles.
- Compared microbial associations and machine-learning classifiers across studies and sequencing methods.
- Used 5,663 samples from 22 datasets with age-of-onset annotations for the EO-CRC/LO-CRC analysis.
- Also compared tumor-resident microbiomes, dietary associations, and *Fusobacterium* subspecies.

## Main conclusion

The CRC-associated gut microbial signature was highly reproducible and nearly identical between early- and late-onset cases. The results support a broadly shared CRC microbiome rather than separate age-specific signatures.

## Figure 2 discussion

**Figure 2: “Gut microbial signatures of EO-CRC and LO-CRC are highly similar.”**

- **A:** Forest plots compare differentially abundant genera in EO-CRC and LO-CRC using linear mixed models and study-specific estimates.
- **B:** Genus-level CRC enrichment effects show similar direction and magnitude between the two onset groups.
- **C:** Disease status explains more relevant bacterial abundance variation than age at diagnosis.
- **D:** A classifier trained on LO-CRC transfers to EO-CRC with performance similar to EO-CRC cross-validation.
- **E:** Random-forest SHAP importance values are concordant between EO-CRC and LO-CRC models.

Recurring influential genera include *Fusobacterium*, *Peptostreptococcus*, *Parvimonas*, and *Porphyromonas*.

## Questions for discussion

- Does similarity at the genus level exclude meaningful strain-level or functional differences?
- How effectively do the mixed models separate age from cohort, geography, diet, and sequencing platform?
- Could a shared classifier improve screening in younger patients, or would age-specific calibration still be required?
- How should the modest disease-associated effect be interpreted relative to the much larger study effect in Bray–Curtis ordination?
- Which findings are associative, and which are plausible targets for mechanistic validation?

## Meeting notes

- Presenter:
- Meeting date:
- Key points raised:
- Follow-up papers or analyses:
