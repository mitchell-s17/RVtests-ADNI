# Rare Variant Association Analysis with RVtests (ADNI)

This notebook provides a full workflow for rare variant burden testing in the ADNI dataset using PLINK data with RVtests.

## Workflow Overview

### 1. Data Preparation & QC
- Perform PLINK-based QC for rare (MAF 0.005–0.01) and common variants
- LD pruning and PCA generation for population structure control
- Generate phenotype, covariate, and keep files for AD vs CN baseline samples

### 2. Dataset Conversion
- Filter rare variant dataset to matched samples
- Convert PLINK binary files to VCF, followed by compression and indexing

### 3. Association Testing (RVtests)
- Gene-based rare variant testing using:
  - CMC (burden test)
  - SKAT-O (kernel test)
  - Variable Threshold (Price)
- Adjusts for covariates (age, sex, education, APOE4, PCs)

### 4. Post-Analysis
- Aggregate and compare results across tests
- Identify genes significant in multiple methods
- Export summary statistics and significant findings

### 5. Variant Extraction
- Extract significant loci from VCF using bcftools
- Apply allele frequency filters for rare variant validation
- Generate RSID lists for candidate genes


---

### Citations

> Petersen RC, et al. Alzheimer's Disease Neuroimaging Initiative. Alzheimers Dement. 2010 May;6(3):238-46. </p>
> Xiaowei Zhan, et al. RVTESTS: An Efficient and Comprehensive Tool for Rare Variant Association Analysis Using Sequence Data. Bioinformatics. 2016 32: 1423-1426.
