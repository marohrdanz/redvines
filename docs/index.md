
## Next-Generation Clustered Heat Map (NG-CHM) R Package

This page is about the [NGCHM R package](https://github.com/MD-Anderson-Bioinformatics/NGCHM-R),
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

- [Create a NG-CHM](/redvines/create-a-ng-chm): Create a NG-CHM and export as a stand-alone HTML file or as a .nghcm file to load to the [NG-CHM  viewer](https://www.ngchm.net/Downloads/ngChmApp.html).


[Back to top](#)
