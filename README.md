---
title: " Mass-spec proteomics: Focal adhesion kinase (FAK) in adipose cells"
author:
  name: "Dmytro Kryvokhyzha"
email: dmytro.kryvokhyzha@med.lu.se
affiliation: LUDC Bioinformatics Unit
date: "10 January, 2024"
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

Prior experiments indicate that cytoskeleton pathways could be affected.

## Analysis

Permormed with the [DEP](https://bioconductor.org/packages/release/bioc/html/DEP.html) package in R:


```bash
R -e 'rmarkdown::render("code/proteomic_FAK_adipose.Rmd", output_dir="results/reports/")'
```

Results:

  - `results/reports/proteomic_mass_spec.Rmd` - report of the analysis.
