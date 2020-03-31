---
layout: post
title: Subsetting a wide data.frame in R
categories: data
tags: [R, software]
language: en
---

Subsetting a wide data.frame by it's column names can be achieved in various ways[^source].

[^source]: Examples are [based on a SO discussion.](https://stackoverflow.com/questions/45109061/how-do-you-subset-a-data-frame-based-on-column-names)

### Prelude
Remove all objects from your workspace (if any):

	ls()
	rm(list = ls())
	ls()

Create demo df: 
```r
df <- structure(list(Server = structure(c(1L, 1L, 1L, 1L, 1L, 1L), .Label = "servera", class = "factor"), 
    Date = structure(1:6, .Label = c("7/13/2017 15:01", "7/13/2017 15:02", 
    "7/13/2017 15:03", "7/13/2017 15:04", "7/13/2017 15:05", 
    "7/13/2017 15:06"), class = "factor"), Host_CPU = c(1.812950134, 
    2.288070679, 1.563278198, 1.925239563, 5.350669861, 2.612503052
    ), UsedMemPercent = c(38.19, 38.19, 38.19, 38.19, 38.19, 
    38.22), jvm1 = c(10.91, 11.13, 11.34, 11.56, 11.77, 11.99
    ), jvm2 = c(11.47, 11.7, 11.91, 12.13, 12.35, 12.57), jvm3 = c(75.65, 
    76.88, 56.93, 58.99, 65.29, 67.97), jvm4 = c(39.43, 40.86, 
    42.27, 43.71, 45.09, 45.33), jvm5 = c(27.42, 29.63, 31.02, 
    32.37, 33.72, 37.71)), .Names = c("Server", "Date", "Host_CPU", 
"UsedMemPercent", "jvm1", "jvm2", "jvm3", "jvm4", "jvm5"), class = "data.frame", row.names = c(NA, 
-6L))
ls()
head(df)
```

df2 is the same as df1 except it has fewer columns

```r
df2 <- structure(list(Server = structure(c(1L, 1L, 1L, 1L, 1L, 1L), .Label = "servera", class = "factor"), 
    Date = structure(1:6, .Label = c("7/13/2017 15:01", "7/13/2017 15:02", 
    "7/13/2017 15:03", "7/13/2017 15:04", "7/13/2017 15:05", 
    "7/13/2017 15:06"), class = "factor"), Host_CPU = c(1.812950134, 
    2.288070679, 1.563278198, 1.925239563, 5.350669861, 2.612503052
    ), UsedMemPercent = c(38.19, 38.19, 38.19, 38.19, 38.19, 
    38.22), jvm3 = c(75.65, 76.88, 56.93, 58.99, 65.29, 67.97
    ), jvm4 = c(39.43, 40.86, 42.27, 43.71, 45.09, 45.33), jvm5 = c(27.42, 
    29.63, 31.02, 32.37, 33.72, 37.71)), .Names = c("Server", 
"Date", "Host_CPU", "UsedMemPercent", "jvm3", "jvm4", "jvm5"), class = "data.frame", row.names = c(NA, 
-6L))
ls()
head(df2)
```
The objective is to reproduce df2 by subsetting df1:

## Method 1 - plain R
reproduce df2 by selecting named columns

```r
select <- c("Server","Date","Host_CPU","UsedMemPercent",
            "jvm3","jvm4","jvm5")
df[select]
```

### Note 1: vectors as opposed to data.frame

We are using built-in iris df

	str(iris)

Use `[[ ]]` if you want a single column in the form of a vector:

	iris[["Species"]]

print unique vector levels

	levels(iris[["Species"]])

this is same as:

	levels(iris$Species)

You can use this vector for subsetting

	vl <- levels(iris$Species)
	vl[[1]]

## Method 2 using `dplyr` package

	library(dplyr)
	select(df, Server,Date,Host_CPU,UsedMemPercent,jvm3,jvm4,jvm5)