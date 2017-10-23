
<!-- README.md is generated from README.Rmd. Please edit that file -->
prcr
====

`prcr` is an `R` package for person-centered analysis. Person-centered analyses focus on clusters, or profiles, of observations, and their change over time or differences across factors. See [Bergman and El-Khouri (1999)](http://onlinelibrary.wiley.com/doi/10.1002/(SICI)1521-4036(199910)41:6%3C753::AID-BIMJ753%3E3.0.CO;2-K/abstract) for a description of the analytic approach. See [Corpus and Wormington (2014)](http://www.tandfonline.com/doi/abs/10.1080/00220973.2013.876225) for an example of person-centered analysis in psychology and education.

Installation
------------

You can install prcr from github with:

``` r
# install.packages("devtools")
devtools::install_github("jrosen48/prcr")
```

You can install prcr from CRAN with:

``` r
install.packages("prcr")
```

Example
-------

This is a basic example which shows you how to solve a common problem:

``` r
library(dplyr)
#> 
#> Attaching package: 'dplyr'
#> The following objects are masked from 'package:stats':
#> 
#>     filter, lag
#> The following objects are masked from 'package:base':
#> 
#>     intersect, setdiff, setequal, union
library(prcr)

create_profiles(iris, Sepal.Length, Sepal.Width, Petal.Length, Petal.Width, n_profiles = 3) %>% 
    select(-Species) %>% 
    group_by(profile) %>%
    summarize_all(mean)
#> Fit model with 3 profiles using the 'constrained variance' model.
#> Model BIC is 813.051
#> # A tibble: 3 x 5
#>   profile Sepal.Length Sepal.Width Petal.Length Petal.Width
#>     <dbl>        <dbl>       <dbl>        <dbl>       <dbl>
#> 1       1        5.006    3.428000     1.462000    0.246000
#> 2       2        5.920    2.752727     4.323636    1.350909
#> 3       3        6.680    3.017778     5.617778    2.073333
```

Vignettes
---------

See examples of use of prcr in the [Introduction to prcr](https://jrosen48.github.io/prcr/articles/introduction_to_prcr.html) vignettes.

Code of Conduct
---------------

Please note that this project is released with a Contributor Code of Conduct. By participating in this project you agree to abide by its terms below. This Code of Conduct is adapted from the Contributor Covenant (<http:contributor-covenant.org>), version 1.0.0, available at <http://contributor-covenant.org/version/1/0/0/>

> As contributors and maintainers of this project, we pledge to respect all people who contribute through reporting issues, posting feature requests, updating documentation, submitting pull requests or patches, and other activities. We are committed to making participation in this project a harassment-free experience for everyone, regardless of level of experience, gender, gender identity and expression, sexual orientation, disability, personal appearance, body size, race, ethnicity, age, or religion. Examples of unacceptable behavior by participants include the use of sexual language or imagery, derogatory comments or personal attacks, trolling, public or private harassment, insults, or other unprofessional conduct. Project maintainers have the right and responsibility to remove, edit, or reject comments, commits, code, wiki edits, issues, and other contributions that are not aligned to this Code of Conduct. Project maintainers who do not follow the Code of Conduct may be removed from the project team. Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by opening an issue or contacting one or more of the project maintainers.
