---
title: "Next-Generation (Clustered) Heat Maps R Package"
date: 2020-02-11
draft: false
bread: "NG-CHM R"

description: "An R package for creating Next-Generatiopn Clustered Heat Maps (NG-CHMs)"
href:
language: "R"
current-version: "0.12.8"
platforms:
license:
status: "Active"
last-updated: "2020-08-15"
citation: [
    [ 'Bradley M. Broom, Michael C. Ryan, Robert E. Brown, Futa Ikeda, Mark Stucky, David W. Kane, James Melott, Chris Wakefield, Tod D. Casasent, Rehan Akbani and John N. Weinstein, *A Galaxy Implementation of Next-Generation Clustered Heatmaps for Interactive Exploration of Molecular Profiling Data*. Cancer Research 77(21): e23-e26 (2017).', 'http://cancerres.aacrjournals.org/content/77/21/e23' ],
    [ 'Michael C. Ryan, Mark Stucky, Chris Wakefield, James M. Melott, Rehan Akbani, John N. Weinstein, and Bradley M. Broom, *Interactive Clustered Heat Map Builder: An easy web-based tool for creating sophisticated clustered heat maps*. F1000Research 2019, 8 (ISCB Comm J):1750.', 'https://doi.org/10.12688/f1000research.20590.1' ]
]
news: 
github: MD-Anderson-Bioinformatics/NGCHM-R
image: "/public-software/ngchm/317px-NG-CHM-V2_Screenshot.png"
contact: ["Bradley M. Broom", "bmbroom@mdanderson.org"]
discussion: https://github.com/MD-Anderson-Bioinformatics/NGCHM-R/issues
---

## Next-Generation Clustered Heat Map (NG-CHM) R Package

This page is about the {{< link text="NGCHM R package" url="https://github.com/MD-Anderson-Bioinformatics/NGCHM-R" >}},
which can be used to construct [Next-Generation Clustered Heat Maps]({{< ref "/public-software/ngchm" >}}), and contains the
following sections:

- [Package Installation in R](#package-installation-in-r)
- [Using the Docker Image](#using-the-docker-image)
- [Vignettes](#vignettes)

## Package Installation in R 


#### System Requirements

- R >= 3.5
- Java >= 8
- git, tar, scp, ssh
  - Mac/Linux: typically installed by default
  - Windows: Cygwin or Windows Subsystem for Linux (Windows 10)
- C compiler
  - Mac: Xcode
  - Linux: gcc
  - Windows: Rtools or Rtools40 (Windows 10)
- R package {{< link text="bmbroom/tsvio" url="https://github.com/bmbroom/tsvio" >}}
  - This package requires a C compiler
- R package {{< link text="NGCHMSupportFiles" url="https://github.com/MD-Anderson-Bioinformatics/NGCHMSupportFiles" >}}
  - This package requires Java to use
  - This package contains a compiled .jar file and minified JavaScript file


#### Installation 

The above-mentioned R packages can be installed from GitHub with
{{< link text="remotes" url="https://cran.r-project.org/web/packages/remotes/index.html" >}}:

```{R}
remotes::install_github('bmbroom/tsvio')
remotes::install_github('MD-Anderson-Bioinformatics/NGCHMSupportFiles', ref='main')
remotes::install_github('MD-Anderson-Bioinformatics/NGCHM-R')
```

## Using the Docker Image

There is also a Docker image containing RStudio, the NGCHM-R package, and all needed dependencies 
available on {{< link text="Docker Hub" url="https://hub.docker.com/r/ngchm/rstudio-ngchm" >}}.

The YouTube Video, {{< link text="How to Create Next-Generation Clustered Heat Map in R Studio" url="https://www.youtube.com/watch?v=O42w5P3A1_8&t=37s" >}}, 
details usage of the Docker image. Further installation and usage information is available 
in ths the {{< link text="RStudio NGCHM" url="https://github.com/MD-Anderson-Bioinformatics/rstudio-ngchm" >}}
project on GitHub.



## Vignettes

- [Create a NG-CHM](/public-software/ngchm-r/create-a-ng-chm): Create a NG-CHM and export as a stand-alone HTML file or as a .nghcm file to load to the {{< link text="NG-CHM  viewer" url="https://www.ngchm.net/Downloads/ngChmApp.html" >}}
- [Covariate Bars and Discrete Color Maps](/public-software/ngchm-r/covariate-bars-and-discrete-color-maps): Add covariate bars and specify their color map
- [Continuous Color Maps and Data Layers](/public-software/ngchm-r/continuous-color-maps-and-data-layers): Add multiple data layers and specify their color map
- [Clustering and Column/Row Ordering](/public-software/ngchm-r/clustering-and-column-row-ordering): Specify options for clustering/ordering rows and columns
- [Adding Linkouts](/public-software/ngchm-r/adding-linkouts): Add linkouts to row and column labels


[Back to top](#)
