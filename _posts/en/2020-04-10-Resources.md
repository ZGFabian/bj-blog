---
layout: post
title: Resources for R statistics
categories: data
tags: [R, rstats, tidyverse, SPSS, packages]
language: en
---

The road from proprietary tools toward FOSS is long and far from being straightforward. There is no single Golden Path (as in Buddhism or in Kabbalah) or a yellow brick road for Dorothy as in the classic tale of The Wizzard Oz. It is especially true for R's jungle-like ecosystem where tidyverse packages occupy more and more space. [cf. this not to recent SO post](https://stackoverflow.blog/2017/10/10/impressive-growth-r/) 

## Data sources
 - lodown [Analyze Survey Data for Free](http://asdfree.com/prerequisites.html) - online book by [Anthony Damico](http://www.ajdamico.com/). 
 		- [github](https://github.com/ajdamico/lodown/tree/master/R)
 - WDI
 - eurostat
 - wb
 - gapminder

## Tidyverse 
 - https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Tidyverse+Cheat+Sheet.pdf
 - https://www.datacamp.com/community/blog/tidyverse-cheat-sheet-beginners

## Nomenclatures
 - countrycodes
 - fuzzy cntr codes TODO

## Data manipulations
 - dplyr: [cheat-sheet](https://github.com/rstudio/cheatsheets/blob/master/data-transformation.pdf)
 - tidyr 

## Data import
 - foreign
 - haven translates "value labels into a new labelled() class, which preserves the original semantics and can easily be coerced to factors with as_factor(). Special missing values are preserved." [haven.tidyverse.org](https://haven.tidyverse.org/)
 - readr
 - data.table::fread()

## Plotting & visualization
 - ggplot2: [cheat-sheet](https://rstudio.com/wp-content/uploads/2016/11/ggplot2-cheatsheet-2.1.pdf)
 		- another [cheats](https://github.com/sefakilic/ggplot-cheatsheet)
 		- [ggplot2 workshop part 1](https://youtu.be/h29g21z0a68) by Thomas Lin Pedersen (@thomasp85)
 - extrafonts
 - gganimate 
 		- [barchart race](https://evamaerey.github.io/little_flipbooks_library/racing_bars/racing_barcharts.html#1)
 - ggbump
 - patchwork
 - ggforce
 - dashboards flex TODO
 - [ggdag](https://github.com/malcolmbarrett/ggdag) by Malcolm Barett

## Styled tables
 - pander with pandoc
 - DT with jquery "The R package DT provides an R interface to the JavaScript library DataTables. R data objects (matrices or data frames) can be displayed as tables on HTML pages, and DataTables provides filtering, pagination, sorting, and many other features in the tables." [Tutorial & docs](https://rstudio.github.io/DT/)
 - gt [twitter](https://twitter.com/riannone/status/1247963802550833152)
 - xtables

## SPSS related
 - expss (TODO)
 - foreign (import that use pspp method for SPSS formats)
 - memisc
 - SPSStoR (for learning R and dplyr syntax)
 - gmodels (esp. CrossTable function, which is "an implementation of a cross-tabulation function with output similar to S-Plus crosstabs() and SAS Proc Freq (or SPSS format) with Chi-square, Fisher and McNemar tests of the independence of all table factors."[documentation](https://www.rdocumentation.org/packages/gmodels/versions/2.18.1/topics/CrossTable)

## Survey data analysis
 - survey
 - survyr (tidyverse implemntation of survey package)
 - memisc
 - dplyr (there are some weighted function that can be appropriate for point estimates)

## blog and authoring (based on markdown and pandoc)
 - blogdown
 - bookdown
 - rmarkdown
 - pander
 - knitR
 - xaringan
 - Tufte handout
<!--- this is going to be a new post 
## learning R
 - datacamp
 - R4DS
 - coding style guides
 - Lander Analytics YT channel
 - (https://zenartofrpkgs.netlify.app/)
 --->
