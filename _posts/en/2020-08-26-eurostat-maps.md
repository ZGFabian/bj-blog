---
title: Mapping Eurostat data
subtitle: using R's eurostat, sf and ggplot2 packages
categories: data
tags: [ggplot, sf, eurostat, mapping]
lang: en
image: /bj-blog/img/20-08-26-eurostat/emp-small.gif
---

Recently, I found a [post](https://rpubs.com/muuankarski/210495) on mapping Eurostat data, which was written in 2016 by [Markus Kainu](https://github.com/muuankarski). It is not too old, but an important function within `{eurostat}` package became obsolote since then. `merge_eurostat_geodata()` have been abondoned because of switching to [simple features](https://r-spatial.github.io/sf/articles/sf1.html) standard. After some searching I found a solution to this issue[^issue]. (It also turned out that Markus Kainu is one of the devs of `{eurostat}`.) So, I made some minor changes in the original code base in order to reproduce and update some of the maps on NUTS2 (regional) level.

Here they are (Click to enlarge image):
{% include image-gallery.html folder="/bj-blog/img/20-08-26-eurostat/" %}

I think they are quite pretty, although not fully comparable due to different value categories.

{: .box-note}
### Class struggle: Mind your objects' classes!

Plotting sf objects is easy with ggplot and geom_sf() unless you mess your data classes.
Pay special attention when you join data.frames of different classes. Consider the following scenarios:

![codepic](/bj-blog/img/20-08-26-eurostat/join-code.png)

As long as you get "sf", you are good to go forward with geom_sf. Otherwise you'll be stucked.


More info:

 - [`{sf}` source on github](https://github.com/r-spatial/sf)
 - [`{eurostat}` source on github](https://github.com/rOpenGov/eurostat)
 - [`{sf}` cheet sheet](https://github.com/rstudio/cheatsheets/blob/master/sf.pdf)
 - [`{eurostat}` cheet sheet](https://raw.githubusercontent.com/rstudio/cheatsheets/master/eurostat.pdf)

 [^issue]: [on merge_eurostat_geodata](https://github.com/rOpenGov/eurostat/issues/146)

![gif](/bj-blog/img/20-08-26-eurostat/emp-small.gif)

Full source as gist:

<script src="https://gist.github.com/ZGFabian/2171e506ac444aeb7ed3edb80fe97574.js"></script>

