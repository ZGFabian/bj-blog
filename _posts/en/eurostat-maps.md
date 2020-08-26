---
title: Mapping Eurostat data 
subtitle: using E's eurostat, sf and ggplot2 packages
categories: data
tags: [ggplot, sf, eurostat, mapping]
lang: en
---

Recently, I found a post on mapping Eurostat data, which was written in 2016 by [Markus Kainu](https://github.com/muuankarski). It is not too old, but since than some important function within `{eurostat}` package became obsolote. An important function `merge_eurostat_geodata()` have been abondoned because of switching to [simple features](https://r-spatial.github.io/sf/articles/sf1.html) standard. After some searching I found a solution at this issue[^issue]. (It also turn out that Markus Kainu is one of the devs of `{eurostat}`. So, I made some minor changes in the original code base in order to reproduce and update some of the maps on NUTS2 (regional) level. 

Here they are:
![2015 employment pic](/img/20-08-26-eurostat/2015-eu-unemp-2020-08-26.png)
![2019 employment pic](/img/20-08-26-eurostat/2019-eu-unemp-2020-08-26.png)

Class struggle: Mind your objects' classes!
Plotting sf objects is easy with ggplot and geom_sf() unless you mess your data classes.
Pay special attention when you join data.frames of different classes. Consider the following scenarios: 

![codepic](/img/20-08-26-eurostat/join-code.png)

As long as you get "sf", you are good to go forward with geom_sf. Otherwise you'll be stucked.


More info:

 - [`sf` package source on github](https://github.com/r-spatial/sf)
 - [eurostat package source on github](https://github.com/rOpenGov/eurostat)
 - [sf cheet sheet](https://github.com/rstudio/cheatsheets/blob/master/sf.pdf)
 - [eurostat cheet sheet](https://raw.githubusercontent.com/rstudio/cheatsheets/master/eurostat.pdf)
 
 [^issue]: [on merge_eurostat_geodata](https://github.com/rOpenGov/eurostat/issues/146)

Full source as gist:



```r
	sessionInfo()
	R version 4.0.2 (2020-06-22)
	Platform: x86_64-pc-linux-gnu (64-bit)
	Running under: Manjaro Linux
	
	Matrix products: default
	BLAS:   /usr/lib/libblas.so.3.9.0
	LAPACK: /usr/lib/liblapack.so.3.9.0
	
	locale:
	 [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C               LC_TIME=en_US.UTF-8       
	 [4] LC_COLLATE=en_US.UTF-8     LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
	 [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                  LC_ADDRESS=C              
	[10] LC_TELEPHONE=C             LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
	
	attached base packages:
	[1] stats     graphics  grDevices utils     datasets  methods   base     
	
	other attached packages:
	[1] sf_0.9-5       stringr_1.4.0  ggplot2_3.3.2  dplyr_1.0.1    eurostat_3.6.1
```