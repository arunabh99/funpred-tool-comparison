# funpred-tool-comparison
This repository contains code for the study evaluating the concordance between 16S rRNA-based
functional predictions (PICRUSt2, Tax4Fun2) and measured stool metabolomics.

## Overview

The pipeline predicts KO abundances from 16S data with PICRUSt2 and Tax4Fun2,
then compares them against measured metabolites across four cohorts using three
analyses: maximum KO-metabolite correlation, targeted (KEGG reaction-based)
correlation, and community metabolic modelling with MIMOSA2. A shotgun
metagenomics cohort is included as a reference.

## Scripts

Run in order after setting paths in `config.R`.

1. `01_run_predictions.R`: generate PICRUSt2 and Tax4Fun2 KO profiles
2. `02_load_and_harmonize.R`: load and align KO, metabolite, and mapping tables
3. `03_max_correlation.R`: maximum KO-metabolite correlation
4. `04_targeted_correlation.R`: targeted correlation via KEGG mappings
5. `05_mimosa_prep.R`: prepare MIMOSA2 inputs
6. `06_mimosa_analysis.R`: MIMOSA2 results and MGM classification
7. `07_summary.R`: combined summary across analyses
8. `08_shotgun_analysis.R`: shotgun reference analysis

`config.R` holds paths, shared settings, and helper functions.

## Data

Input data are from the curated microbiome-metabolome resource:
https://github.com/borenstein-lab/microbiome-metabolome-curated-data
