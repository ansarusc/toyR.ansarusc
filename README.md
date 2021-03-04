
<!-- README.md is generated from README.Rmd. Please edit that file -->

# toyR.ansarusc

<!-- badges: start -->

<!-- badges: end -->

The goal of toyR.ansarusc is to …

## Installation

You can install the released version of toyR.ansarusc from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("toyR.ansarusc")
```

And the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("ansarusc/RpckgAnsaru17")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(toyR.ansarusc)
## basic example code
```

## Quick demo

Binding two factors via `fbind()`:

``` r
library(toyR.ansarusc)
a <- factor(c("character", "hits", "your", "eyeballs"))
b <- factor(c("but", "integer", "where it", "counts"))
```

Simply catenating two factors leads to a result that most don’t expect.

``` r
c(a, b)
#> [1] 1 3 4 2 1 3 4 2
```

The `fbind()` function glues two factors together and returns factor.

``` r
fbind(a, b)
#> [1] character hits      your      eyeballs  but       integer   where it 
#> [8] counts   
#> Levels: but character counts eyeballs hits integer where it your
```

Often we want a table of frequencies for the levels of a factor. The
base `table()` function returns an object of class `table`, which can be
inconvenient for downstream work.

``` r
set.seed(1234)
x <- factor(sample(letters[1:5], size = 100, replace = TRUE))
table(x)
#> x
#>  a  b  c  d  e 
#> 19 19 21 22 19
```

The `fcount()` function returns a frequency table as a tibble with a
column of factor levels and another of frequencies:

``` r
fcount(x)
#> # A tibble: 5 x 2
#>   f         n
#>   <fct> <int>
#> 1 d        22
#> 2 c        21
#> 3 a        19
#> 4 b        19
#> 5 e        19
```
