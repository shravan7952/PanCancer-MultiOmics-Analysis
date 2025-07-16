# Pan-Cancer Multi-Omics Analysis: Unraveling Cancer's Complexity

## Project Overview

This repository contains the code and resources for an independent project focused on leveraging multi-omics data from The Cancer Genome Atlas (TCGA) to classify diverse tumor types, identify critical molecular biomarkers, and analyze the impact of the Tumor Microenvironment (TME) on patient survival. The project is structured into three distinct phases, each building upon the insights of the previous one.

## Project Phases

### Phase 1: Pan-Cancer Classification and Biomarker Discovery

Focuses on integrating various omics data types (gene expression, mutations, CNV, methylation, miRNA, RPPA proteomics) to develop robust machine learning models for precise tumor type classification. It also identifies key molecular biomarkers and investigates misclassification patterns.

### Phase 2: Tumor Microenvironment (TME) Analysis

Delves into the composition of the TME using xCell deconvolution data. This phase analyzes TME score distributions, identifies distinct TME clusters, and examines immune checkpoint gene expression and their correlations.

### Phase 3: Dedicated Survival Analysis based on TME Clusters

Explores the prognostic value of the identified TME clusters by correlating them with patient overall survival data using Kaplan–Meier curves and Cox Proportional Hazards models. This phase provides crucial insights into how TME composition influences patient outcomes.

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/PanCancer-MultiOmics-Analysis.git
cd PanCancer-MultiOmics-Analysis
```

### 2. Set Up Your Python Environment

It is recommended to use a virtual environment.

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows:
.\venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Dependencies

The Python package requirements for this project are:

* pandas
* numpy
* matplotlib
* seaborn
* scipy
* gseapy
* statsmodels
* umap-learn
* scikit-learn
* joblib

You can install them all using:

```bash
pip install -r requirements.txt
```

To generate or update `requirements.txt`:

```bash
pip freeze > requirements.txt
```

---

## Data Requirements

Due to large file sizes, TCGA datasets are not included in this repository. Please download the following files manually from the [TCGA Pan-Cancer (PANCAN) cohort on UCSC Xena](https://xenabrowser.net/datapages/?cohort=TCGA%20Pan-Cancer%20%28PANCAN%29&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443).

Place **all files in the root directory** of the repository (at the same level as the phase folders and notebooks).

### Required Files

* **Gene Expression (RNA-Seq)**
  `EB++AdjustPANCAN_IlluminaHiSeq_RNASeqV2.geneExp.xena`

* **Somatic Mutations**
  `mc3.v0.2.8.PUBLIC.maf`

* **Copy Number Variation (CNV)**
  `Gistic2_CopyNumber_Gistic2_all_data_by_genes`
  `Gistic2_CopyNumber_Gistic2_all_thresholded.by_genes`

* **DNA Methylation (450K)**
  `jhu-usc.edu_PANCAN_HumanMethylation450.betaValue_whitelisted.tsv.synapse_download_5096262.xena`

* **miRNA Expression**
  `pancanMiRs_EBadjOnProtocolPlatformWithoutRepsWithUnCorrectMiRs_08_04_16.xena`

* **RPPA Proteomics**
  `TCGA-RPPA-pancan-clean.xena`

* **Phenotype and Subtype Files**
  `TCGA_phenotype_denseDataOnlyDownload.tsv`
  `TCGASubtype.20170308`
  `Subtype_Immune_Model_Based` *(optional/custom)*

* **Survival Data**
  `Survival_SupplementalTable_S1_20171025_xena_sp`

* **xCell Deconvolution Output**
  `xcell_deconvoluted.csv`

* **MSigDB Gene Sets for GSEA** (download from [MSigDB](https://www.gsea-msigdb.org/gsea/msigdb/index.jsp))
  `h.all.v7.5.1.symbols.gmt`
  `c2.cp.kegg.v2023.1.Hs.entrez.gmt`

> **Note**: As of now, this repository only includes the phase notebooks and the xCell deconvolution output file. You will need to manually download and place the rest of the datasets.

---

## Directory Structure

```
PanCancer-MultiOmics-Analysis/
│
├── EB++AdjustPANCAN_IlluminaHiSeq_RNASeqV2.geneExp.xena
├── mc3.v0.2.8.PUBLIC.maf
├── Gistic2_CopyNumber_Gistic2_all_data_by_genes
├── Gistic2_CopyNumber_Gistic2_all_thresholded.by_genes
├── jhu-usc.edu_PANCAN_HumanMethylation450.betaValue_whitelisted.tsv.synapse_download_5096262.xena
├── pancanMiRs_EBadjOnProtocolPlatformWithoutRepsWithUnCorrectMiRs_08_04_16.xena
├── TCGA-RPPA-pancan-clean.xena
├── TCGA_phenotype_denseDataOnlyDownload.tsv
├── TCGASubtype.20170308
├── Subtype_Immune_Model_Based
├── Survival_SupplementalTable_S1_20171025_xena_sp
├── xcell_deconvoluted.csv
│
├── h.all.v7.5.1.symbols.gmt
├── c2.cp.kegg.v2023.1.Hs.entrez.gmt
│
├── phase1_pan_cancer_classification/
│   └── phase1_code.ipynb
│
├── phase2_tme_analysis/
│   └── phase2_code.ipynb
│
├── phase3_survival_analysis/
│   └── phase3_code.ipynb
│
├── results/
│   ├── tme_analysis/
│   ├── gsea/
│   ├── summary_tables/
│
├── graphs/
├── plots/
├── docs/
│   └── blog_post_phase3.md
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Running the Analysis

To run each phase of the analysis:

1. Activate your virtual environment
2. Launch Jupyter Notebook

```bash
jupyter notebook
```

3. Navigate to one of the following folders:

* `phase1_pan_cancer_classification/`
* `phase2_tme_analysis/`
* `phase3_survival_analysis/`

4. Open and execute the corresponding notebook (e.g., `phase1_code.ipynb`) step-by-step.

> **Note**: All required plots and visualizations will be automatically generated when you run the notebooks across Phases 1, 2, and 3.

---

## Related Articles

Explore the blog posts and case studies based on this project:

### Medium Articles

* [Unraveling Cancer's Complexity: Pan-Cancer Multi-Omics + ML](https://medium.com/@shravan0601200/unraveling-cancers-complexity-a-solo-journey-through-pan-cancer-multi-omics-and-machine-learning-5d39f5c697c3)
* [Tumor Microenvironment Analysis – Phase 2](https://medium.com/@shravan0601200/unraveling-cancers-complexity-a-solo-journey-through-the-tumor-microenvironment-phase-2-e746deecf25f)
* [TME & Survival – Phase 3](https://medium.com/@shravan0601200/unraveling-cancers-complexity-a-solo-journey-through-the-tumor-microenvironment-phase-3-b1c026d3fe23)

### LinkedIn Articles

* [Tumor Microenvironment Analysis (Phase 2)](https://www.linkedin.com/pulse/unraveling-cancers-complexity-solo-journey-through-tumor-shravan-s-flqdc)
* [Pan-Cancer Multi-Omics (Phase 1)](https://www.linkedin.com/pulse/unraveling-cancers-complexity-solo-journey-through-pan-cancer-s-onafc)

---

## Contact

For questions or collaboration inquiries, please contact:

**Name**: Shravan Srikanthan
**Email**: [shravan06010200@gmail.com](mailto:shravan06010200@gmail.com)
**LinkedIn**: [https://www.linkedin.com/in/shravan-s-7b53a494/](https://www.linkedin.com/in/shravan-s-7b53a494/)

---
