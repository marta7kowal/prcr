# prcr

`prcr` is an `R` package for person-centered analysis. Person-centered analyses focus on clusters, or profiles, of observations, and their change over time or differences across factors. See [Bergman and El-Khouri (1999)](http://onlinelibrary.wiley.com/doi/10.1002/(SICI)1521-4036(199910)41:6%3C753::AID-BIMJ753%3E3.0.CO;2-K/abstract) for a description of the analytic approach. See [Corpus and Wormington (2014)](http://www.tandfonline.com/doi/abs/10.1080/00220973.2013.876225) for an example of person-centered analysis in psychology and education.

Because this package is in development and is not yet available on CRAN, to install it, first install the `devtools` package using `install.packages("devtools")`, followed by the function `devtools::install_github("jrosen48/prcr")`. After installing the package, use `library(prcr)` to load it each session.

This package is organized around four functions:

* `prepare_data()`

  * This function inputs a `data.frame` or `matrix` of at least two columns, as well as strings indicating the method of centering, the grouping factor (used only for group-mean centering), and the method of scaling. It outputs a `list` to be used in the `create_profiles()` function.

* `create_profiles()`

  * This function inputs the list generated by the `prepare_data()` function, as well as an integer indicating the number of clusters, or profiles, selected a priori, the distance metric, and the linkage method. Its output is a `list` with two items, one for the output of the hierarchical cluster analysis, and one for the output of the k-means cluster analysis.

* `calculate_stats()`

  * This function inputs the `list` generated from `create_profiles`. It outputs a `list` with 10 items, including fit indices and a plot of the cluster centroids to be used in diagnosing the adequacy of the solution generated from the `create_profiles()` function.

* `explore_factors()`

  * This function inputs the cluster assignments and the attributes indicating which cases to keep from the `calculate_stats()` function, as well as a data frame of factors to explore, a string indicating the specific factor to explore (or a vector indicating the factors to explore), and an optional vector of names for the cluster solution generated from the `create_profiles()` function.

The basic workflow is to first prepare the data (by removing incomplete cases and centering and / or scaling the data) with `prepare data()`, to create profiles with the `create_profiles()` function, calculate statistics about the profiles using the `calculate_stats()` function, and explore the distribution of profiles across select factors with the `explore_factors()` function. To review arguments and basic documentation for each function, call each prefaced with `?`, i.e. `?prepare_data()`.
