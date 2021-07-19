---
title: "Next-Generation (Clustered) Heat Maps R Package"
date: 2020-02-11
draft: false
bread: "Create a NG-CHM"

---

## Create a NG-CHM

This vignette demonstrates how to construct a simple NG-CHM and 
save it as a file that can be opened in the {{< link text="NG-CHM Viewer" url="https://www.ngchm.net/Downloads/ngChmApp.html" >}}. The following sections are below:

- [Sample NG-CHM Data](#sample-ng-chm-data)
- [Creating a NG-CHM](#creating-a-ng-chm)
- [Export to File](#export-to-file)

### Sample NG-CHM Data

This vignette uses an additional package of demo data, {{< link text="NGCHMDemoData" url="https://github.com/MD-Anderson-Bioinformatics/NGCHMDemoData" >}}, 
which can be installed from GitHub with {{< link text="remotes"  url="https://cran.r-project.org/web/packages/remotes/index.html" >}}:

```{r}
remotes::install_github('MD-Anderson-Bioinformatics/NGCHMDemoData', ref='main')
```

and loaded into the current environment:

```{r}
library(NGCHMDemoData)
```

The sample data includes a matrix of mRNA expression data, TCGA.GBM.Expression, for 3540 genes (rows) and 169 samples 
(columns) from the Glioblastoma Multiforme TCGA data. **In order to be used as the basis for an NG-CHM, a matrix should have both
rownames and colnames.** Here the rownames are genes and the colnames are TCGA sample identifiers:

```{r}
TCGA.GBM.ExpressionData[1:4,1:2]
#           TCGA-06-0178-01A-01R-1849-01 TCGA-02-2483-01A-01R-1849-01
# TNFAIP8L3                   0.04324498                  -1.12556612
# SYK                        -0.12174522                   0.03007443
# C2                          0.07445546                  -0.21648993
# ACP5                        1.45195866                   0.12276042
```

The sample data also includes a vector of TP35 mutation status for the TCGA samples in the matrix. This 
data will be used to construct a covariate bar in 
[Covariate Bars and Discrete Color Maps](/public-software/ngchm-r/covariate-bars-and-discrete-color-maps). 
**In order to be used as the basis for a covariate bar,
a vector should have at least one name in common with the colnames of the matrix.**

```{r}
TCGA.GBM.TP53MutationData[1:2]
# TCGA-06-0178-01A-01R-1849-01 TCGA-02-2483-01A-01R-1849-01 
#                        "WT"                        "MUT" 
```

[Back to top](#)

### Creating a NG-CHM

Using the data loaded above, the chmNew() function can be used to create an NG-CHM:

```{r}
library(NGCHM)
hm <- chmNew('tcga-gbm', TCGA.GBM.ExpressionData)
```

[Back to top](#)

### Export to File

The NG-CHM created above can be exported to two different file types:

1. A stand-alone HTML file that can be emailed to collaborators and opened in a standard browser.
2. A '.ngchm' file that can be opened in the {{< link text="NG-CHM Viewer" url="https://www.ngchm.net/Downloads/ngChmApp.html" >}}.

Both methods use files from the
{{< link text="NGCHMSupportFiles" url="https://github.com/MD-Anderson-Bioinformatics/NGCHMSupportFiles" >}} package referenced
in the [installation instructions](/public-software/ngchm-r/#package-installation-in-r). When loaded, NGCHMSupportFiles 
sets a two environment variables that point to these additional files.

```{r}
library(NGCHMSupportFiles)
```

The NG-CHM can be exported as a stand-alone HTML file with the chmExportToHTML() funciton.
The first argument is the NG-CHM created above. The second argument is the desired filename,
and the third is a boolean dictating if any existing file of that name should be overwritten.

```{r}
chmExportToHTML(hm,'tcga-gbm.html',overwrite=TRUE)
```

The file 'tcga-gbm.html' can be shared with collaborators and opened in a standard web browser.

Alternatively, .ngchm file can be created with the chmExportToFile() function.


```{r}
chmExportToFile(hm,'tcga-gbm.ngchm',overwrite=TRUE)
```

The file 'tcga-gbm.ngchm' can be opened in the {{< link text="NG-CHM Viewer" url="https://www.ngchm.net/Downloads/ngChmApp.html" >}}.
**NOTE: The filename must end with '.ngchm' to open in the NG-CHM Viewer**. 



[Back to top](#)

