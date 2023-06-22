## Status

<!-- badges: start -->
[![R-CMD-check](https://github.com/seandavi/GEOquery/workflows/R-CMD-check/badge.svg)](https://github.com/seandavi/GEOquery/actions)
<!-- badges: end -->

## Installation

To install directly from github:

```{r}
# Install remotes from CRAN if you have not installed 'remotes'
install.packages("remotes")
# Download modified GEOquery package from github by using function(install_github()) from 'remotes' package. 
library(remotes)
install_github("curryhank08/GEOquery_without_timeout", force = TRUE)

```
## Way to set max timeout_seconds before downloading data
Since GEOquery_without_timeout/R/getGEOfile.R was modified in line 185 as :
"timeout_seconds <- max(getOption("timeout"), 120)"
, we have to set timeout seconds before running getGEO().

Shown as below:
```{r}
# Load modified GEOquery
library(GEOquery)
# Setting the max timeout_seconds
options(timeout=100000)
# Check the input timeout_seconds
getOption("timeout")
```

## Usage

See the full vignette in [rmarkdown](https://github.com/seandavi/GEOquery/blob/master/vignettes/GEOquery.Rmd) or visit Bioconductor for details:

- [Release version](http://www.bioconductor.org/packages/release/bioc/html/GEOquery.html)
- [Devel version](http://www.bioconductor.org/packages/devel/bioc/html/GEOquery.html)

## How to contribute

Contributions to GEOquery development can be submitted as a [pull request](https://github.com/seandavi/GEOquery/pulls) or a [feature request issue](https://github.com/seandavi/GEOquery/issues). We recommend following the [Bioconductor coding standards](https://contributions.bioconductor.org/r-code.html) where possible.  
