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
### Concept
Since GEOquery_with_modifiable_timeout_seconds/R/getGEOfile.R was modified in line 185 as :
```{r}
timeout_seconds <- max(getOption("timeout"), 120)
```
, compared to original code :
```{r}
timeout_seconds <- 120
```
, we have to set timeout seconds before running getGEO().
### Steps shown as below:
```{r}
# Load modified GEOquery
library(GEOquery)

# Setting the max timeout_seconds
options(timeout=100000)

# Check the input timeout_seconds (Optional)
getOption("timeout")
```
## References
https://github.com/seandavi/GEOquery/pull/139,
https://www.jianshu.com/p/2bbc8f9a473f

## Usage

See the full vignette in [rmarkdown](https://github.com/seandavi/GEOquery/blob/master/vignettes/GEOquery.Rmd) or visit Bioconductor for details:

- [Release version](http://www.bioconductor.org/packages/release/bioc/html/GEOquery.html)
- [Devel version](http://www.bioconductor.org/packages/devel/bioc/html/GEOquery.html)
