---
title: " Mass-spec proteomics: Focal adhesion kinase (FAK) in adipose cells"
author:
  name: "Dmytro Kryvokhyzha"
email: dmytro.kryvokhyzha@med.lu.se
affiliation: LUDC Bioinformatics Unit
date: "28 February, 2024"
output:
  html_document:
    keep_md: true
---
  


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

Performed with the [DEP](https://bioconductor.org/packages/release/bioc/html/DEP.html) package in R:


```bash
R -e 'rmarkdown::render("code/proteomic_FAK_adipose.Rmd", output_dir="results/reports/")'
```

Results:

  - `results/reports/proteomic_FAK_adipose.html` - report of the analysis.
  
  - `results/reports/proteomic_FAK_adipose_noIP1.html` - report of the analysis without IP1.
  
  - `results/table/proteomic_FAK_adipose_results.tsv` - results table.
  
  - `results/table/proteomic_FAK_adipose_results_noIP1.tsv` - results table without IP1.
