# Community Ecology Basics
Nilanjan Chatterjee

## Nestedness
Nestedness is a measure of structure in an ecological system. 
There are different measures for nestedness. One common measure is calculating the temperature. 
We will use that measure to calculate nestedness here. The value ranges from 0-100 where 0 stands for perfectly nested community and 100 stands for random community

Vegan is one the most important library for analysis of community dataset. The most common type of community data is sites x species data. We would uploda a dummy dataset in the system and leran how to calculate nestedness.

##Import the data in R 
```{r }
library(vegan)
setwd("C:/Users/HP/Documents/com_eco")
bhagbird <-read.csv("allbird_38.csv")
head(bhagbird)

```

## Calculating nestedness
```{r}
nesttry<-nestedtemp(bhagbird[,2:15])
nesttry
```
