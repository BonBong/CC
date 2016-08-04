ELISA comparing expression in HEK 293 and HEK Gqi cells (FuGENE)
================
Bongani Mveng
21 July 2016

``` r
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
library(knitr)
library(readr)

CCR52 <- read.csv("ELISA comparing CCR5 expression in HEK 293 adnd HEK Gqi cells (FuGENE).csv")
CCR52
```

    ##     Transfection HEK.293.absorbance HEK.Gqi.absorbance
    ## 1  Untransfected              0.309              0.205
    ## 2  Untransfected              0.219              0.212
    ## 3  Untransfected              0.295              0.216
    ## 4  Untransfected              0.216              0.204
    ## 5  Untransfected              0.325              0.189
    ## 6  Untransfected              0.224              0.195
    ## 7        WT CCR5              0.495              1.284
    ## 8        WT CCR5              0.470              1.308
    ## 9        WT CCR5              0.499              1.192
    ## 10       WT CCR5              0.514              1.225
    ## 11       WT CCR5              0.563              1.291
    ## 12       WT CCR5              0.597              1.337
    ## 13         Y214A              0.453              1.461
    ## 14         Y214A              0.532              1.364
    ## 15         Y214A              0.493              1.297
    ## 16         Y214A              0.524              1.267
    ## 17         Y214A              0.674              1.396
    ## 18         Y214A              0.618              1.375
    ## 19         Y214N              0.182              0.202
    ## 20         Y214N              0.160              0.191
    ## 21         Y214N              0.179              0.188
    ## 22         Y214N              0.180              0.186
    ## 23         Y214N              0.196              0.210
    ## 24         Y214N              0.183              0.171

``` r
ccr52 <- tbl_df(CCR52)
ccr52
```

    ## Source: local data frame [24 x 3]
    ## 
    ##     Transfection HEK.293.absorbance HEK.Gqi.absorbance
    ##           <fctr>              <dbl>              <dbl>
    ## 1  Untransfected              0.309              0.205
    ## 2  Untransfected              0.219              0.212
    ## 3  Untransfected              0.295              0.216
    ## 4  Untransfected              0.216              0.204
    ## 5  Untransfected              0.325              0.189
    ## 6  Untransfected              0.224              0.195
    ## 7        WT CCR5              0.495              1.284
    ## 8        WT CCR5              0.470              1.308
    ## 9        WT CCR5              0.499              1.192
    ## 10       WT CCR5              0.514              1.225
    ## ..           ...                ...                ...

``` r
par(mfrow = c(1, 2), mar = c(4, 4, 2, 1), oma = c(0, 0, 2, 0))

boxplot(ccr52$HEK.293.absorbance~ccr52$Transfection, xlab = "Transfection", ylab = "Absorbance (at 450 nm)", main = "HEK 293 absorbances", ylim = c(0.2, 1.4))

boxplot(ccr52$HEK.Gqi.absorbance~ccr52$Transfection, xlab = "Transfection", ylab = "Absorbance (at 450 nm)", main = "HEK Gqi absorbances")
 
mtext("ELISA results comparing CCR5 expression in HEK 293 and HEK Gqi cells", outer = TRUE)
```

![](ELISA_comparing_CCR5_expression_in_HEK_293_adnd_HEK_Gqi_cells__FuGENE__files/figure-markdown_github/CCR5%202-1.png)
