---
title       : Earnings Difference
subtitle    : Course Project for Developing Data Products
author      : chang y. chung
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Too Much Ink

1. Often, there are too much information to present.
2. In terms of graphs, this will ends up: too many or too busy.
3. A graph that is too busy (many lines or symbols) is described as "Too much ink"

--- 

## Interactive Graphs To Rescue

1. Interactive graphs let users (readers) to modify some aspects of graphs interactively.
2. This includes changing scales, getting more details of certain points, or picking-and-choosing some of points (lines, or symbols) that they are interested in.

--- .codefont .codemargin .outmargin

## Here is an example of a Too-Much-Ink


```r
cohort <- as.character(seq(1965, 2000, 5))
plot(c(2.43, 4.39, 4.92, 6.72, 5.44, 2.94, 5.44, 2.53), type="b", ylim=c(-20,20), xlab="Cohort", ylab="% Diff", axes=FALSE, pch=1, lty=1)
axis(1, at=1:length(cohort), labels=cohort)
axis(2)
lines(c(-1.59, 0, .3, 1.82, 0.4, -2.08, .2, -2.66), type="b", pch=2, lty=2)
lines(c(-2.66, -.7, -9.43, -14.19, -3.37, -4.5, 1.82, -2.76), type="b", pch=3, lty=3)
lines(c(-6.39, -4.88, -13.32, -18.21, -8.24, -9.06, -3.25, -7.96), type="b", pch=4, lty=4)
lines(c(.4, -15.8, -10.86, -7.6, 2.53, 13.88, 15.37, 8.55), type="b", pch=5, lty=5)
lines(c(-3.15, -19.1, -14.53, -11.57, -1.98, 8.87, 10.19, 3.67), type="b", pch=6, lty=6)
legend("topleft", legend=c("English-speaking Caribbean vs. Native Blacks", "English-speaking Caribbean vs. Native Black Movers", "Latin American vs. Native Blacks", 
"Latine American vs. Native Black Movers", "English-speaking African vs. Native Blacks", "English-speaking Aftrican vs. Native Black Movers"), pch=1:6, lty=1:6)
```

![plot of chunk unnamed-chunk-1](assets/fig/unnamed-chunk-1.png) 

---

## Re-draw as an Interactive Graph

1. Previous line graphs into two bar graphs: three comparison groups on each graph, according to the baseline group (Native Black and Native Black Movers)
2. Let readers (users) pick how many "series" of bars to show (can select from one to all three)
3. Use well-chosen colors consistantly for the comparison groups.
4. Remove redundant words and simplify the labels.
5. Convert the graph into a simple app using shiny, and host it at shinyapps.io.
6. See the result at https://chang-y-chung.shinyapps.io/gaps/
