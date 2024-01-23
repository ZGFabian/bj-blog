---
title: Over or below the red line
subtitle: Mortality in Hungary and in the USA during the pandemic
categories: data
tags: [ggplot, COVID-19, mortality, USA, EUROMOMO]
lang: en
image: /img/20-10-07-mortality/hu-mortality-w36-small.png
comments: true
date: 2020-10-12
excerpt: Current and historical mortality data can be used for assessing the net cost of current pandemic. Hungarian data for the first eight months are favourable compared to the US. However the infection curves are rising in several EU countries while the spread of the virus seems to be slowing down in the States.   
---
Summary: Current and historical mortality data can be used for assessing the net cost of current pandemic. Hungarian data for the first eight months are favourable compared to the US. However the infection curves are rising in several EU countries while the spread of the virus seems to be slowing down in the States. 

Kieran Healy (@kjhealy) recently [tweeted](https://twitter.com/kjhealy/status/1313276959263162368){:target="blank"} and [published](https://kieranhealy.org/blog/archives/2020/09/24/us-excess-mortality/){:target="_blank"} some shocking charts on US weekly mortality numbers that showed the high cost of current pandemic in terms of mortality surplus. Compared to previous years the overall picture looks like this (*Figure 1*): 


### Figure 1
[![US weekly mortality by @kjhealy](/img/20-10-07-mortality/USAmortality.jpg)](/img/20-10-07-mortality/USAmortality.jpg)

As he wrote: "Everyone under that red line was a real person. Hundreds of thousands of people are dead, and every one of them was as real as you. Brave or fearful, weak or tough, flamboyant or shy, the virus doesn't give a shit." 

I have plotted a similar chart for Hungary using [weekly mortality data from the Central Statistical Office](https://www.ksh.hu/docs/hun/xstadat/xstadat_evkozi/e_wnh004a.html){:target="_blank"}. 

The overall picture of 2020 mortality is still favorable (*Figure 2*) - nobody is under the red line. Yet. However, take a look at the infection curve which is rising sharply (*Figure 3*) in Hungary and in it's neighbours while the curve seems to be flattening in the US. 
### Figure 2
[![Hungary-weekly-mortality](/img/20-10-07-mortality/hu-mortality-w36-2020-10-12.png)](/img/20-10-07-mortality/hu-mortality-w36-2020-10-12.png)

### Figure 3
[![Hungary-new-cases
](/img/20-10-07-mortality/c19-cases-2020-10-12.png)](/img/20-10-07-mortality/c19-cases-2020-10-12.png)

Figure 4 shows the monthly mortality rates per thousands. Data is from the CSO STADAT [1.1 table](https://www.ksh.hu/docs/hun/xstadat/xstadat_evkozi/e_wdsd001a.html){:target="_blank"}.

### Figure 4
[![Hungary-mortality-rates
](/img/20-10-07-mortality/hu-mortality-rate-2020-10-12.png)](/img/20-10-07-mortality/hu-mortality-rate-2020-10-12.png)

Note that Figures 1, 2 and 4 comparing historical trends within one country and doesn't tell us much about cross-country differences.

With different methodologies similar comparisons are available for European countries from the [EUROMOMO](https://www.euromomo.eu/graphs-and-maps) project. A sample chart is shown in *Figure 5*. 

### Figure 5
[![overall-mortality-euromomo](/img/20-10-07-mortality/euromomo-zoom.png)](/img/20-10-07-mortality/euromomo-zoom.png)

Sources:

- [R-script](/img/20-10-07-mortality/weekly-mortality.R) 

Data:

- [weekly numbers]((/img/20-10-07-mortality/weekly-total-deaths.csv)) 
- [monthly rates](/img/20-10-07-mortality/monthly-deaths.csv).


