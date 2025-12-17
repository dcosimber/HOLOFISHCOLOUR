# Transcriptomic Analysis of Pigmentation Disorders in Turbot (*Scophthalmus maximus*)

## Project: HOLOFISHCOLOUR  
**Task 3 – Transcriptomic Characterization (RNA-seq)**

---

## 1. Objectives

The main objective of this task was to generate a comprehensive transcriptomic profile of selected tissues from normally pigmented and pseudo-albino turbot (*Scophthalmus maximus*), in order to:

- Characterize global gene expression patterns associated with pigmentation phenotypes.
- Identify differentially expressed genes between normally pigmented and malpigmented individuals.
- Explore molecular pathways potentially involved in pseudo-albinism and pigmentation disorders.

This task comprised the following steps:

1. RNA isolation and quality assessment.  
2. RNA library construction and high-throughput sequencing.  
3. Bioinformatic processing and differential expression analysis.

---

## 2. Experimental Design and Sampling

### 2.1 Biological Material

Three individuals per phenotype (normal vs pseudo-albino) were selected from tanks **E6** and **E8**, where pigmentation differences were most pronounced.

- **Tank E6:** offspring from two different parental pairs.  
- **Tank E8:** half-sib family (shared mother, two different fathers).

From each individual, **skin and intestine** samples were collected.

---

### 2.2 Sample Types and Pigmentation Categories

- **Normally pigmented fish:**
  - Pigmented skin (dark) on the ocular side
  - Non-pigmented skin (light) on the blind side

- **Pseudo-albino fish:**
  - Pigmented and non-pigmented skin on both ocular and blind sides

---

### 2.3 Sample Overview

**Table 1. Samples selected for transcriptomic analysis**

| Sample ID | Tissue | Tank | Individual | Pigmentation phenotype | Body side | Color |
|---------|--------|------|-----------|------------------------|-----------|-------|
| P31 | Skin | E6 | 46 | Normal | Ocular | Dark |
| P32 | Skin | E6 | 46 | Normal | Blind | Light |
| P33 | Skin | E8 | 52 | Normal | Ocular | Dark |
| P34 | Skin | E8 | 52 | Normal | Blind | Light |
| P41 | Skin | E8 | 142 | Malpigmented | Ocular | Dark |
| P42 | Skin | E8 | 142 | Malpigmented | Ocular | Light |
| P43 | Skin | E8 | 142 | Malpigmented | Blind | Dark |
| P44 | Skin | E8 | 131 | Malpigmented | Blind | Light |
| P45 | Skin | E6 | 130 | Malpigmented | Ocular | Dark |
| P46 | Skin | E6 | 130 | Malpigmented | Ocular | Light |
| P47 | Skin | E6 | 130 | Malpigmented | Blind | Dark |
| P48 | Skin | E6 | 130 | Malpigmented | Blind | Light |

---

## 3. Sample Collection

### 3.1 Skin Sampling

Fish were maintained at −80 °C and placed on ice prior to sampling to prevent rapid thawing. While still frozen, approximately **20 mg of skin tissue** were excised using sterile dissection tools.

Muscle tissue was carefully removed by gentle scraping to avoid contamination.

![Skin sampling procedure](figures/Figure_1_skin_sampling.png)

*Figure 1. Skin sampling for transcriptomic analysis. A–B: Sampling areas in pseudo-albino and normally pigmented turbot. Areas outlined with yellow dashed lines correspond to non-pigmented skin, whereas areas outlined in red correspond to pigmented skin. C: Skin incision and sample collection.*

---

### 3.2 Intestinal Sampling

Intestinal samples were obtained by ventral dissection. The visceral mass was removed, and intestinal contents were gently expelled before collecting the posterior intestine segment.

![Intestine sampling procedure](figures/Figure_15_intestine_sampling.png)

*Figure 2. Intestinal sampling procedure.*

---

## 4. RNA Extraction and Quality Assessment

### 4.1 RNA Isolation

Total RNA was extracted using a **TRIzol™ + Phasemaker™ Tubes** protocol, followed by purification with the **RNeasy Mini Kit (Qiagen)**.

RNA concentration was measured using **NanoDrop™ One**, and integrity was assessed by **1.5% agarose gel electrophoresis**.

---

### 4.2 RNA Extraction Quality Metrics

**Table 2. RNA concentration and purity metrics**

| Sample | Concentration (ng/µl) | A260/A280 | A260/A230 |
|------|----------------------|-----------|-----------|
| P31 | 1142.7 | 2.14 | 2.10 |
| P32 | 813.4 | 2.14 | 2.18 |
| P33 | 338.9 | 2.12 | 2.24 |
| P34 | 440.5 | 2.10 | 2.27 |
| P35 | 299.3 | 2.12 | 1.08 |
| P36 | 308.8 | 2.13 | 2.18 |

---

## 5. RNA-Seq Library Preparation and Sequencing

RNA sequencing was performed by **Novogene (WOBI service)** using strand-specific mRNA libraries.

### 5.1 Sequencing Specifications

**Table 3. RNA-seq technical specifications**

| Parameter | Description |
|---------|-------------|
| Platform | NovaSeq X Plus |
| Read type | Paired-end (PE150) |
| Library type | Directional mRNA (polyA enrichment) |
| Quality threshold | Q30 ≥ 85% |
| Data output | ≥ 6 Gb per sample |
| Number of samples | 50 |

---

## 6. RNA Quality Control (Bioanalyzer)

RNA integrity was evaluated using the **Agilent 5400 Bioanalyzer**, generating RNA Integrity Number (RIN) values.

- Most samples showed **RIN values between 7.0 and 9.8**, suitable for RNA-seq.
- Sample **IT12 (RIN = 3.8)** failed QC and was excluded.
- Sample **IT16 (RIN = 6.0)** showed moderate degradation and was also discarded.

![RNA Bioanalyzer profiles](figures/Figure_20_RNA_QC.png)

*Figure 3. Representative Bioanalyzer electropherograms.*

---

## 7. Reference Genome

RNA-seq analyses were conducted using the **Scophthalmus maximus ASM1334776v1** genome assembly (Ensembl release 113).

### 7.1 Genome Statistics

**Table 4. Reference genome summary**

| Feature | Value |
|------|------|
| Assembly | ASM1334776v1 |
| Genome size | 556,696,898 bp |
| Coding genes | 21,263 |
| Non-coding genes | 12,989 |
| Gene transcripts | 76,329 |
| Annotation source | Ensembl |

The following files were used:

- **Genome FASTA:** `Scophthalmus_maximus.ASM1334776v1.dna.toplevel.fa`
- **Annotation GTF:** `Scophthalmus_maximus.ASM1334776v1.113.gtf`

---

## 8. Bioinformatic Analysis

### 8.1 Overview

The bioinformatic workflow included:

1. Raw read quality control  
2. Alignment to the reference genome  
3. Gene-level quantification  
4. Differential expression analysis  
5. Functional enrichment analysis

![RNA-seq bioinformatic workflow](figures/Flowchart_RNAseq_pipeline.png)

*Figure 4. RNA-seq bioinformatic analysis pipeline.*

---

## 9. Notes and Next Steps

This transcriptomic dataset provides a solid foundation for:

- Integrating GWAS candidate genes
- Cross-validating pigmentation pathways
- Comparative analyses with other flatfish species
- Multi-omics integration within the HOLOFISHCOLOUR framework

Further refinement will include:
- Differential expression results
- GO / KEGG enrichment
- Integration with phenotypic pigmentation metrics

---

*End of document*
