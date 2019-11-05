Nestedness of River Birds Community in Bhagirathi basin
================
Nilanjan Chatterjee
18 March 2019

Defination of Nestedness
------------------------

Nestedness is a measure of structure in an ecological system. There are different measures for nestedness. One common measure is calculating the temperature. We will use that measure to calculate nestedness here. The value ranges from 0-100 where 0 stands for perfectly nested community and 100 stands for random community

Getting the data in R
---------------------

``` r
library(vegan)
```

    ## Loading required package: permute

    ## Loading required package: lattice

    ## This is vegan 2.5-6

``` r
setwd("D:/Work/River bird")
bhagbird <-read.csv("allbird_38.csv")
head(bhagbird)
```

    ##             SITE..500.m.. WCR PWR WW WBW GW BD CK WTK RL I BWT SF LF LC
    ## 1            Triveni ghat   0   1  0   1  0  0  1   1  1 0   1  0  0  1
    ## 2                  Ghat 1   0   1  0   1  1  0  0   1  1 0   1  0  0  1
    ## 3                  Ghat 2   0   1  0   1  1  0  1   0  0 0   1  0  0  1
    ## 4                Ramjhula   0   0  0   1  0  0  1   1  1 0   1  0  0  0
    ## 5  Phoolchatti main river   1   1  0   1  1  1  1   0  0 0   1  0  0  1
    ## 6 Phoolchatti side stream   1   1  0   1  1  1  1   1  0 0   1  1  1  1

Calculating nestedness
----------------------

``` r
nesttry<-nestedtemp(bhagbird[,2:15])
nesttry
```

    ## nestedness temperature: 17.94312 
    ## with matrix fill 0.4450549

Including Plots
---------------

The plots for nestedness temperature is given by Darker the colour means higher the probability of the species extinction from the site

``` r
plot(nesttry, xlab = "Species", ylab="Sites",main="Extinction probability")
```

![](Nestednedss_Riverbirds1_files/figure-markdown_github/unnamed-chunk-3-1.png)

``` r
plot(nesttry, kind="incidence",xlab = "Species", ylab="Sites",main="Presence-absence")
```

![](Nestednedss_Riverbirds1_files/figure-markdown_github/unnamed-chunk-3-2.png)

Reference
---------

Almeida-Neto, M., Guimarães, P., Guimarães, P.R., Loyola, R.D. & Ulrich, W. (2008). A consistent metric for nestedness analysis in ecological systems: reconciling concept and measurement. Oikos 117, 1227-1239.

Almeida-Neto, M. & Ulrich, W. (2011). A straightforward computational approach for measuring nestedness using quantitative matrices. Env. Mod. Software 26, 173-178.

Atmar, W. & Patterson, B.D. (1993). The measurement of order and disorder in the distribution of species in fragmented habitat. Oecologia 96, 373-382.

Baselga, A. (2012). The relationship between species replacement, dissimilarity derived from nestedness, and nestedness. Global Ecol. Biogeogr. 21, 1223-1232.

Brualdi, R.A. & Sanderson, J.G. (1999). Nested species subsets, gaps, and discrepancy. Oecologia 119, 256-264.

Patterson, B.D. & Atmar, W. (1986). Nested subsets and the structure of insular mammalian faunas and archipelagos. Biol. J. Linnean Soc. 28, 65-82.

Rodríguez-Gironés, M.A. & Santamaria, L. (2006). A new algorithm to calculate the nestedness temperature of presence-absence matrices. J. Biogeogr. 33, 924-935.

Stone, L. & Roberts, A. (1990). The checkerboard score and species distributions. Oecologia 85, 74-79.

Wright, D.H., Patterson, B.D., Mikkelson, G.M., Cutler, A. & Atmar, W. (1998). A comparative analysis of nested subset patterns of species composition. Oecologia 113, 1-20.
