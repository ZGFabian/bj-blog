I would like to highlight here the charting capabilities of ggplot, that
are based on different layers containing geoms (lines, points, bars,
etc). In the very basic ggplot declaration there should be an “aesthetic
mapping” that describes how variables in the data are mapped to geoms.
However, additional mappings can be defined in each layers.

We shall create a line chart, which shows the cumulative daily COVID-19
deaths in Visegrad countries, that are Czechia, Hungary, Poland and
Slovakia with R’s ggplot package.

{% include image.html url=“/images/brent-rambo.gif” caption=“Jekyll
rules the world. Your Jekyll friend, Steve” width=410 align=“right” %}

``` r
# setwd("/home/fabian/projects/2020/linechart")
library(tidyverse)
library(extrafont)
# download and read csv file
uri <- c("https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_deaths_global.csv")
uri
```

    ## [1] "https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_deaths_global.csv"

``` r
df <- read_csv(uri)

# some data wrangling - cf. my previous post
df <- df %>% select(-c("Province/State", "Lat", "Long"))
df <- df %>% rename(c("country" = "Country/Region"))
df <- pivot_longer(df, cols = ends_with("20"),
    names_to = "date", values_to = "deaths")
df <- df %>% filter(country == c("Hungary", "Slovakia", "Poland", "Czechia"))
df$date <- as.Date(df$date, "%m/%d/%y")
df <- arrange(df, date, country)
tail(df)
```

    ## # A tibble: 6 x 3
    ##   country  date       deaths
    ##   <chr>    <date>      <dbl>
    ## 1 Czechia  2020-07-14    355
    ## 2 Slovakia 2020-07-14     28
    ## 3 Hungary  2020-07-17    595
    ## 4 Poland   2020-07-17   1612
    ## 5 Czechia  2020-07-18    358
    ## 6 Slovakia 2020-07-18     28

``` r
# create the plot
mycolors <- c("#FF9700", "black", "red", "blue") # define 4 colours for the countries 
p1 <- ggplot(df, aes(date, deaths, group = country))
p1 <- p1 + geom_line(aes(color = country, linetype = country), size = 2) # note that color and line mappings ar inside aes()
p1 <- p1 + geom_point(aes(shape = country, color = country), size = 4) # again: aes () contains mappings
p1 <- p1 + scale_color_manual(values = mycolors) # manual color setting instead of default
p1 <- p1 + scale_linetype_manual(values =
     c("solid", "twodash", "solid", "longdash")) # custom linetype
p1 <- p1 + theme(legend.position = "top", legend.title = element_blank()) # move legend to top & supress legend title
# p1 <- p1 + theme(text = element_text(family = "Ubuntu Mono", size = 12)) # custom TTF font with extrafonts pkg
p1 <- p1 + labs(title = "Number of COVID deaths in V4 countries",
              subtitle = "Cumulative numbers",
              caption = "Data source: JHU")
p1 <- p1 + xlim(x = c(Sys.Date() - 60, NA)) # x scale range: previous 60 days 
p1
```

![](/img/unnamed-chunk-3-1.png)<!-- -->

That’s all. [Download the Rscript file]().
