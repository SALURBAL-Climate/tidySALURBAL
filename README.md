
# ⚠️ In development - highly experimental ⚠️

-----


<!-- README.md is generated from README.Rmd. Please edit that file -->

# tidySALURBAL <img src="man/figures/tidySALURBAL.png" align="right" alt="" width="120" />

<!-- badges: start -->
<!-- badges: end -->

The **tidySALURBAL** package has two goals: 1) to provide utility
functions for the common SALURBAL data cleaning tasks and 2) to allow
users to interface with the SALURBAL data API to return tidyverse-ready
data frames, optionally with feature geometry included.

## Installation

You can install the development version of tidySALURBAL from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("SALURBAL-Climate/tidySALURBAL")
```

To load the package call the following code.

``` r
library(tidySALURBAL)
```

After you have loaded the package you can start using some of the utlity
functions provided. Here are two useful ones.

## sanitize_codebook_var()

`sanitize_codebook_var()` converts existing SALURBAL data identifiers to
FAIR variables aka `var_name`. In the example below we start with the
salurbal data identifier of `APSPM25MEANL1AD` which contains some
geographic information, we then use sanitize_codebook_var() to convert
it to a purely variable identifier.

``` r
sanitize_codebook_var('APSPM25MEANL1AD')
```

    ## [1] "APSPM25MEAN"

## get_uhc_file_path()

For this project we will use the UHC server as our data storage
location. This function just helps generates paths that R can utilize.
This is utilized in our setup chunks.

``` r
get_uhc_file_path(dataset_id = "APSL1AD", file = "APSL1AD_06132022.csv")
```

    ## [1] "\\\\files.drexel.edu\\colleges\\SOPH\\Shared\\UHC\\Projects\\Wellcome_Trust\\Data Methods Core\\Dashboards\\FAIR Renovations\\APSL1AD\\raw-data\\APSL1AD_06132022.csv"
