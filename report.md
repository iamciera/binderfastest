---
title: "Results report: package downloads example"
author: "William Michael Landau"
output: html_document
---



This small data analysis project explores some trends in R package downloads over time. The datasets are downloaded using the [cranlogs package](https://github.com/metacran/cranlogs).


```
##         date count package
## 1 2019-01-05 10490   dplyr
## 2 2019-01-06 10403   dplyr
## 3 2019-01-07 20786   dplyr
## 4 2019-01-08 23565   dplyr
## 5 2019-01-09 26471   dplyr
## 6 2019-01-10 27745   dplyr
## 7 2019-01-11 25958   dplyr
```

Above, each count is the number of times `dplyr` was downloaded from the RStudio CRAN mirror on the given day. To stay up to date with the latest download statistics, we need to refresh the data frequently. With `drake`, we can bring all our work up to date without restarting everything from scratch. 

See the [corresponding chapter of the user manual](https://ropenscilabs.github.io/drake-manual/example-packages.html) for the details. If you wish to tinker with this example yourself, you can generate the [underlying code files](https://github.com/ropensci/drake/tree/master/inst/examples/packages) with `drake_example("packages")` and then step through `run.R`. This `report.Rmd` file does not stand on its own. It is meant to be called through `run.R`. In fact, the `run.R` file has instructions (comments) to walk you through the project.

# Results

We look at download trends in the following packages.


```
## [1] "knitr"   "Rcpp"    "ggplot2"
```

Using the [cranlogs package](https://github.com/metacran/cranlogs), we calculate the mean number of downloads for each package from the RStudio CRAN mirror. We show these averages for the last month,


```
## # A tibble: 3 x 2
##   package mean_downloads
##   <chr>            <dbl>
## 1 ggplot2         16764.
## 2 knitr           12096.
## 3 Rcpp            20163.
```

and from November 1 to December 1 in 2016.


```
## # A tibble: 3 x 2
##   package mean_downloads
##   <chr>            <dbl>
## 1 ggplot2         14641.
## 2 knitr            9069.
## 3 Rcpp            14408.
```

We visualize the daily downloads from the last month,

<img src="Drake-CRAN-downloads_files/figure-html/reportplotrecent-1.png" width="672" />

and from November 1 to December 1 in 2016.

<img src="Drake-CRAN-downloads_files/figure-html/reportplotolder-1.png" width="672" />
