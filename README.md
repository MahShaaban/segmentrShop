![.github/workflows/basic_checks.yaml](https://github.com/MahShaaban/segmentrShop/workflows/.github/workflows/basic_checks.yaml/badge.svg)

# Software Demo: Chromatin segmentation analysis in R

## Description

Chromatin segmentation analysis transforms ChIP-seq data into signals over the genome.  The latter represents the observed states in a multivariate Markov model to predict the underlying (hidden) states of the chromatin. ChromHMM, written in Java, integrates histone modification datasets to learn the chromatin states de-novo. We developed an R package around this program to leverage the existing R/Bioconductor tools and data structures in the context of the segmentation analysis. segmentr wraps the Java modules to call ChromHMM and captures the output in an S3 R object. This allows for iterating with different parameters, which are given in R syntax. Capturing the output in R makes it easier to work with the results and to integrate them in downstream analyses. Finally, segmentr provides additional tools to test, select and visualize the models. To sum, we developed an R package to wrap a popular chromatin segmentation tool and capture the output in R for testing and visualization.

In this demo, a brief introduction of semgnetation analysis and ChromHMM in particlare will be given. Then we will use the segmentr packaged to apply the analysis to a test dataset and explore the output. We will focus on iterating over models with diffferent numbers of to select one the fits the data well and visualizing the results

## Pre-requisites

- Basic knowledge of *R* syntax
- Familiarity ChIP-seq data
- Reading: [Ernst & Kellis, 2012](https://www.nature.com/articles/nmeth.1906)

## Participation

Participants are expected to walk through the code (rmarkdown document). A brief
an introduction will be given at the beginning to introduce the package and
the discussion will be at the end.

To run the materials locally, use the docker image [mahshaaban/segmentrshop](https://github.com/MahShaaban/segmentrshop) and knit the `Rmd` files in `vignettes/` from within Rstudio.

```bash
docker pull mahshaaban/segmentrshop:latest
docker run -e PASSWORD=<a_password> -p 8787:8787 mahshaaban/segmentrshop:latest
```

An RStudio session will be accessible at [https://localhost:8787/](https://localhost:8787/)
in the browser. The login username is always `rstudio` and the password is `<a_password>`.

## *R* / *Bioconductor* packages used

- segmentr

Data management

- GenomicRanges
- AnnotationDbi

Annotation packages

- TxDb.Hsapiens.UCSC.hg18.knownGene
- org.Hs.eg.db

Visualization

- ggplot2
- ggbio

[Time outline](https://www.notion.so/e72e817485a9465daccd16ff41ab97ee)

## Demo objectives

This demo aims to teach participants how to use perform chromatin segmentation analysis of histone modification data in R. They will use the segmentr package to call ChromHMM and capture the output in an R object. They will also learn to select an appropriate number of states to segment the genome and visualize the results of the selected models. By providing a realistic example, participants would be able to understand the analysis workflow and adapt this code to apply it to their own datasets.

## Learning goals

- Use the segmentr package to call ChromHMM
- Understand the structure of the resulting S3 object
- Iterate over models with different number of states
- Compare the models and select an appropriate one
- Visualize the genome segments using ggbio
- Plug the results of ChromHMM in over-represenation analysis
