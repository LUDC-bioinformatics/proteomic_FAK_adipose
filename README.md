---
title: " Mass-spec proteomics: Focal adhesion kinase (FAK) in adipose cells"
author:
  name: "Dmytro Kryvokhyzha"
email: dmytro.kryvokhyzha@med.lu.se
affiliation: LUDC Bioinformatics Unit
date: "03 July, 2024"
output:
  html_document:
    keep_md: true
---
  
## Publication

[Kopietz et al. **Focal Adhesion Kinase Orchestrates GLUT4 Translocation and Glucose Uptake via Cytoskeletal Turnover in Primary Adipocytes**, _FASEB_](https://doi.org/10.1096/fj.202402764RR)

## PI

Name: **Karin Stenkula**

Email: [karin.stenkula@med.lu.se](mailto:karin.stenkula@med.lu.se)

## Project

Study the role of *focal adhesion kinase* (FAK) in the adipose cells.

Groups:

  - IgG DMSO basal - negative control, no antibodies

  - FAK DMSO basal - basal
 
  - FAK DMSO INS - basal + insulin

  - FAK PF INS - PF (FAK inhibitor) + insulin

Main interest: Do the proteins interacting with FAK differ between the three treatments? 

Prior experiments indicate that cytoskeleton pathways could be affected.

## Analysis

### Differential enrichment analysis 

Performed with the [DEP](https://bioconductor.org/packages/release/bioc/html/DEP.html) package in R:


``` bash
R -e 'rmarkdown::render("code/proteomic_FAK_adipose.Rmd", output_dir="results/reports/")'
```

I removed the sample IP1 because it looked like an outlier. However, the results
for all samples are also provided.

Results:

  - `results/reports/proteomic_FAK_adipose.html` - report of the analysis.
  
  - `results/reports/proteomic_FAK_adipose_noIP1.html` - report of the analysis without IP1.
  
  - `results/table/proteomic_FAK_adipose_results.tsv` - results table.
  
  - `results/table/proteomic_FAK_adipose_results_noIP1.tsv` - results table without IP1.

### Functional analysis

The list of significant proteins was visualized and tested for functional enrichment using [STRING](https://string-db.org).

I used the custom background in the enrichment analysis: *create an account, 
go to MyData -> upload the full list of proteins -> select “enable usage as a statistical background set"
-> select this list in the analysis tab when analyzing a specific set of proteins*

The background is used to correct for the fact that we analysed only subset of proteins 
and some functions could not be included in the analysis or ration between the functions 
is different in our subset versus the whole genome.

The number of background proteins is 666 and thus less than 711 original ones,
because I filter for proteins that are identified in all replicates of at least one condition.

Results:

  - `results/tables/FAK_PF_INS_vs_FAK_DMSO_INS.GO_enrichment.xlsx` - GO enrichment results with BP, MF, and CC tabs.

  - `results/figures/FAK_PF_INS_vs_FAK_DMSO_INS_network.svg` - figure of the full STRING network for significant proteins in the FAK_PF_INS vs FAK_DMSO_INS contrast. The edges indicate both functional and physical protein associations and line thickness indicates the strength of data support.

  - `results/figures/FAK_PF_INS_vs_FAK_DMSO_INS_network_cytoskeleton.svg` - the same figure as above but with highlight in blue of the proteins representing the enriched cytoskeleton GO cellular component term (GO:0005856).
