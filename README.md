# FarMR: Factor-based Multivariable Mendelian Randomization

FarMR is a statistical framework for estimating exposure–outcome causal effects while adjusting for high-dimensional, genetically correlated candidate confounders. It combines genetic factor analysis with empirical-shrinkage multivariable Mendelian randomization (MVMR).

## Motivation

Systematic screening can identify many candidate heritable confounders that share substantial genetic correlation. Including all of these traits in a conventional MVMR model can produce estimates with large standard errors, while selecting only a few representative traits may discard relevant information and introduce subjective analytical choices.

FarMR addresses this challenge by jointly accounting for shared and trait-specific genetic variation, reducing reliance on manual selection of representative confounding traits.

## Method overview

FarMR uses genome-wide association study (GWAS) summary statistics to:

- Represent shared genetic variation across candidate confounding traits using a smaller set of latent factors.
- Retain trait-specific genetic components not explained by those factors.
- Integrate both components into an empirical-shrinkage MVMR model to estimate the exposure’s direct effect on the outcome while accounting for the modeled sources of heritable confounding.

The framework is intended for applications such as biomarker–disease analyses and evaluation of potential causal relationships relevant to therapeutic target research. Interpretation depends on the assumptions of the model, the genetic instruments, and the available data.

## Relationship to esmr and contributions

FarMR was developed by Ruoyao Shi under the supervision of Jean Morrison. Ruoyao’s work includes methodological development, implementation, simulation studies, and applications to GWAS summary data.

FarMR-related code is implemented within the [esmr package](https://github.com/jean997/esmr), which provides empirical-shrinkage methods for Mendelian randomization. This repository is a fork of that package, maintained by Ruoyao Shi to provide a FarMR-focused description and access to the implementation.

The repository retains the upstream esmr code and contribution history. The broader esmr framework and its existing functionality reflect the work of Jean Morrison and other contributors.

## Installation

Install this fork from GitHub:

```r
# Install devtools if needed:
# install.packages("devtools")

devtools::install_github("ruoyao-shi/FarMR")
library(esmr)
```

Although the GitHub repository is named `FarMR`, the R package retains the name `esmr`.

The upstream package vignettes require additional packages that may need to be installed separately:

```r
install.packages(c("DiagrammeR", "reshape2"))
devtools::install_github("jingshuw/grapple")
```

## Project status

FarMR-related code is publicly available in this repository and the upstream esmr repository. The FarMR manuscript is in preparation for posting as a preprint. Additional documentation and reproducible examples are being developed.

## License

This fork retains the upstream esmr license: GPL (>= 3).
