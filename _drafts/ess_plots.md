---
title: Weighted survey means
subtitle: European Social Survey plotting exercise
categories: data
tags: [ggplot, column]
lang: en
---
The following simple example will use European Social Survey (ESS) integrated datafile in order to plot unweighted and weighted distribution of the generalized trust variable (`ppltrst`).
[![question](/img/20-08-11-ess-plots/q_ppltrst.png)](https://www.europeansocialsurvey.org/docs/round1/fieldwork/source/ESS1_source_main_questionnaire.pdf)

Here are the two plots. 

[![p1](/img/20-08-11-ess-plots/p1_small.png)](/img/20-08-11-ess-plots/p1.png)
[![p2](/img/20-08-11-ess-plots/p2_small.png)](/img/20-08-11-ess-plots/p2.png)

The underlying codes demonstrate how to use `srvyr` and `dplyr` to work together on survey data. R can be difficult when it is about weighted sample data. Although `survey` package has been around quite long, but its usage is not straightforward.  This package is particularly useful for analyses of *complex* sampling design's (eg. multi-staged cluster sample). `Srvyr` adds some useful features that fits well into tidyverse workflow. Instead of going to details I forward you to the following useful resources:

1. [Weighting European Social SurveyData](https://www.europeansocialsurvey.org/docs/methodology/ESS_weighting_data_1.pdf)
2. [Federico Vegetti: Survey Weights with R](https://federicovegetti.github.io/teaching/heidelberg_2018/lab/sst_lab_day2.html)
3. Kieran Healy: Data Visualization. (See. Chapter on ["Plots from complex surveys"](https://socviz.co/index.html))
4. Thomas Lumley. 2010. [Complex Surveys: A Guide to Analysis Using R](https://onlinelibrary.wiley.com/doi/book/10.1002/9780470580066)

Data are downloadable from ESS site after registration. I will use a subsample of four (V4) countries and limited number of columns.   

First read SPSS labelled data with haven package functions:
```r
iess <- read_sav("data/ESS1-8e01.sav") %>% as_factor()
```
Note that `as_factor`function converts all haven labelled columns to factors and user-missing values (like 88=DK) to `NA`.

    # A tibble: 51,263 x 40
       cntry cname cedition cproddat cseqno name  essround edition  idno
       <fct> <chr> <chr>    <chr>     <dbl> <chr> <fct>    <chr>   <dbl>
     1 Czec… ESS1… 1.0      12.12.2…  51660 ESS1… 1        6.6         1
     2 Czec… ESS1… 1.0      12.12.2…  51661 ESS1… 1        6.6         2
     3 Czec… ESS1… 1.0      12.12.2…  51662 ESS1… 1        6.6         3
     4 Czec… ESS1… 1.0      12.12.2…  51663 ESS1… 1        6.6         4
     5 Czec… ESS1… 1.0      12.12.2…  51664 ESS1… 1        6.6         7
     6 Czec… ESS1… 1.0      12.12.2…  51665 ESS1… 1        6.6         8
     7 Czec… ESS1… 1.0      12.12.2…  51666 ESS1… 1        6.6         9
     8 Czec… ESS1… 1.0      12.12.2…  51667 ESS1… 1        6.6        10
     9 Czec… ESS1… 1.0      12.12.2…  51668 ESS1… 1        6.6        16
    10 Czec… ESS1… 1.0      12.12.2…  51669 ESS1… 1        6.6        17
    # … with 51,253 more rows, and 31 more variables: dweight <dbl>,
    #   pspwght <dbl>, pweight <dbl>, netuse <fct>, ppltrst <fct>,
    #   pplfair <fct>, pplhlp <fct>, trstprl <fct>, trstlgl <fct>,
    #   trstplc <fct>, trstplt <fct>, trstprt <fct>, trstep <fct>,

Than we prepare data with dplyr "verbs" and calculate unweighted means by `cntry` and `essround`.
```r
d1 <- iess %>%
  select(ppltrst, cntry, essround) %>%
  group_by(cntry, essround) %>%
  summarise(ppl_mean = mean(as.numeric(ppltrst), na.rm = TRUE))
pandoc.table(head(d1))
```
    -------------------------------
      cntry    essround   ppl_mean
    --------- ---------- ----------
     Czechia      1        5.254
     Czechia      2        5.163
     Czechia      4        5.668
     Czechia      5        5.506
     Czechia      6        5.357
     Czechia      7        5.479
    -------------------------------

The plots will be drawn by `geom_col()` which uses values (such as "mean", "sd", whatever values) in `d1` dataframe (ie. "stat_identity") rather than number of cases (using "stat_count"). See details [here](https://ggplot2.tidyverse.org/reference/geom_bar.html). There will be four facets (sub-plots) for each country.

```r
# Labels
ppl_tit <- attr(iess$ppltrst, "label")
subt <- "mean values of a 0-10 scale"
capt <- "Source: ESS integrated file (rounds 1-8)"
xl <- "ESS rounds"
yl <- "mean on 0-10 scale"
# Colors
my_cols <- c("#F07430", "#B03030", "#2D7174", "darkgrey")
p1 <- d1 %>%
  ggplot(aes(x = essround,
             y = ppl_mean,
             label = format(round(d1$ppl_mean, 2), nsmall = 2),
             fill = cntry)) +
    geom_col() +
    # remove letter 'a' from legend key
    geom_label_repel(show.legend = FALSE, vjust = -0.5) +
    scale_fill_manual(name = NULL, values = my_cols) +
    facet_wrap(~ cntry)
p1 <- p1 + labs(title = ppl_tit,
         subtitle = subt,
         caption = capt,
         x = xl,
         y = yl
         )
p1 <- p1 + theme(text = element_text(size = 16,  family = "Ubuntu Mono"))
p1
```

### Unweighted means of generalized trust in V4 countries, 2002-2016

![p1](/img/20-08-11-ess-plots/p1.png)

```r
d1w <- iess %>%
  as_survey(weights = c(pspwght)) %>%
  select(ppltrst, cntry, essround) %>%
  group_by(cntry, essround) %>%
  summarise(ppl_wmean = survey_mean(as.numeric(ppltrst),
                                    na.rm = TRUE, vartype = "ci"))
pandoc.table(head(d1w))
```


    ----------------------------------------------------------------
      cntry    essround   ppl_wmean   ppl_wmean_low   ppl_wmean_upp
    --------- ---------- ----------- --------------- ---------------
     Czechia      1         5.292         5.136           5.447
     Czechia      2         5.295         5.189           5.401
     Czechia      4         5.769         5.637           5.901
     Czechia      5         5.567         5.455           5.679
     Czechia      6         5.414         5.293           5.535
     Czechia      7         5.546         5.433           5.66
    ----------------------------------------------------------------

```r
p2 <- d1w %>%
  ggplot(aes(x = essround,
             y = ppl_wmean,
             ymin = ppl_wmean_low,
             ymax = ppl_wmean_upp,
             label = format(round(d1w$ppl_wmean, 1), nsmall = 1),
             fill = cntry)) +
    geom_col() +
    geom_errorbar(width = 0.4) +
    scale_fill_manual(name = "country", values = my_cols) +
    facet_wrap(~ cntry)

p2 <- p2 + labs(title = ppl_tit,
         subtitle = subt,
         caption = capt,
         x = xl,
         y = yl
         )
p2 <- p2 + theme(text = element_text(family = "Ubuntu Mono"))
```

![p2](/img/20-08-11-ess-plots/p2.png)
