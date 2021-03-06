---
layout: page
title: Programming with R
subtitle: Packages
minutes: 15
---

> ## Objectives {.objectives}
> * What is a package
> * Install packages from a repository
> * Load a package
> * Update packages

### R packages

While R has many features to perform statistical tests, elaborate
plotting, ... out of the box, one reason for its success is the
*easiness* with which it can be expanded by writing **packages** that
extend its functionality.

These packages are writting by thousands of developers and distributed
through on-line repositories. The main repository is the
[Comprehensive R Archive Network](http://cran.r-project.org/), which
has many mirrors across the world. Others include the
[Bioconductor](http://bioconductor.org/), dedicated for the analysis
and comprehension of high-throughput genomic data or general purpose
repositories such as [GitHub](https://github.com/). 

### Installing packages

To install packages from CRAN, one only needs to know the package name
as, for example, `ggplot2` below. 


```r
install.packages("ggplot2")
```

The package is then installed in a specific directory on your hard
drive, called a library.

> ## Tip {.callout}
>
> Note that the first time you install a package, you might get asked
> if you want to create your own personal library in your home
> directory, which is recommended.

### Loading a package

To make use of the functionality of a package, you will need to load
it explicitly every time you start R as shown below:


```r
library("ggplot2")
```

### Installing more packages

To install a package from Bioconductor, you will need a special
function called `biocView` (which uses `install.packages`). The very
first time we want to install a Bioconductor package, we do the
following:


```r
source("http://www.bioconductor.org")
biocLite("DESeq2")
```

After this, we use a dedicated package (which is automatically
installed by `source("http://www.bioconductor.org")`) called
`BiocInstaller`, that provides the `biocLite` function.


```r
library("BiocInstaller")
biocLite("DESeq2")
```

To install a package directly from `GitHub`, we need to use the
`install_github` function from the `devtools` package.


```r
install.packages("devtools")
library("devtools")
install_github("hadley/stringr")
```

> ## Note {.callout}
>
> Packages on CRAN and Bioconductor are reviewed and automatically
> tested before being distributed. Packages on GitHub are not reviewed
> but sometimes get tested automatically.


### Updating packages

Use the `update.packages()` function.
