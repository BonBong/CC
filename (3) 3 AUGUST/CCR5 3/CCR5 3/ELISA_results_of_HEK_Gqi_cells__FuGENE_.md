ELISA results of HEK Gqi cells (FuGENE)
================
Bongani Mveng
August 3, 2016

``` r
library(readr)
ccr5.3 <- read.csv("ELISA results of HEK Gqi cells (FuGENE) 03.08.csv")


library(tidyr)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library(ggplot2)

# print in data frame format

ccr53 <- tbl_df(ccr5.3)
ccr53
```

    ## Source: local data frame [16 x 2]
    ## 
    ##    Transfection Absorbance.at.450nm
    ##          <fctr>               <dbl>
    ## 1        MPP 11               0.145
    ## 2        MPP 11               0.147
    ## 3        MPP 11               0.152
    ## 4        MPP 11               0.149
    ## 5       WT CCR5               0.942
    ## 6       WT CCR5               0.851
    ## 7       WT CCR5               0.935
    ## 8       WT CCR5               1.055
    ## 9         Y214A               1.286
    ## 10        Y214A               1.239
    ## 11        Y214A               1.056
    ## 12        Y214A               1.006
    ## 13        Y214N               0.799
    ## 14        Y214N               0.860
    ## 15        Y214N               0.743
    ## 16        Y214N               0.789

``` r
# plot the data

qplot(x = Transfection,
      y = Absorbance.at.450nm,
      data = ccr53,
      geom = "boxplot",
      main = "ELISA results of HEK Gqi")
```

![](ELISA_results_of_HEK_Gqi_cells__FuGENE__files/figure-markdown_github/CCR5%203-1.png)
