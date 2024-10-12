---
title: Why we expect "group differences" to be zero
author: admin
date: '2020-12-08'
draft: True
slug: why-we-expect-group-differences-to-be-zero
categories: [main]
tags:
  - drift
  - genetic drift
subtitle: ''
summary: ''
authors: []
lastmod: '2020-12-08T23:50:29-05:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
output: blogdown::html
comments: True
---


```r
library(dplyr)
library(ggplot2)
library(data.table)

F = rprojroot::is_rstudio_project$make_fix_file()
```



```r
ancestral.pop = rep(0.5,1e3)

#function to let each locus drift for t generations and ne effective population size
let.it.drift = function(t, ne, trace = FALSE){
  f0 = ancestral.pop
  
  if(trace == FALSE){
    for(i in 1:t){
      f0 = sapply(f0, function(x){
        fx = mean(rbinom(ne, 1, x))
        return(fx)
      })
    }
    return(f0)
    }else{ #
    fmat = matrix(NA, nrow = t, ncol = length(f0))
    for(i in 1:t){
      f0 = sapply(f0, function(x){
        fx = mean(rbinom(ne, 1, x))
        return(fx)
      })
      fmat[i,] = f0
    }
    fmat = reshape2::melt(fmat)
    colnames(fmat) = c("g","locus","frequency")
    return(fmat)
  }
}
```



```r
px = let.it.drift(10, 100, trace = TRUE)

px.mean = px %>%
  group_by(g)%>%
  summarize(frequency = mean(frequency))
```

```
## `summarise()` ungrouping output (override with `.groups` argument)
```

```r
ggplot(px)+
  geom_line(aes(g,
                frequency,
                group = locus),
            color = "grey",
            alpha = 0.5)+
    geom_line(data = px.mean, 
            aes(g, frequency),
            color = "blue")+
  theme_classic()+
  labs(x = "Generations",
       y = "Frequency")
```

<img src="{{< relref "post/2020-12-08-why-we-expect-group-differences-to-be-zero/index.en.markdown" >}}index.en_files/figure-html/unnamed-chunk-3-1.png" width="672" />

You see that blue line? That represents the mean frequency across all replicates and it stays very close to 0.5, despite the fact that the frequency of each replicate changes wildly around 0.5. 


```r
p.12 = data.table(
  p1 = let.it.drift(10,100, trace = FALSE),
  p2 = let.it.drift(10,100, trace = FALSE)
)

p.12 = p.12 %>%
  mutate(p1_2 = p1 - p2)

ggplot(p.12)+
  geom_histogram(aes(p1 - p2),
                 fill = "grey",
                 color = "black")+
  geom_vline(
    aes(xintercept = mean(p1 - p2)),
    color = "red")+
  theme_classic()+
  labs(x = "Difference in allele frequency",
       y = "Count")
```

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

<img src="{{< relref "post/2020-12-08-why-we-expect-group-differences-to-be-zero/index.en.markdown" >}}index.en_files/figure-html/unnamed-chunk-4-1.png" width="672" />


```r
ggplot(p.12)+
  geom_histogram(aes(abs(p1 - p2)),
                 fill = "grey",
                 color = "black")+
  geom_vline(
    aes(xintercept = mean(abs(p1 - p2))),
    color = "red")+
  theme_classic()+
  labs(x = "Absolute difference in allele frequency")
```

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

<img src="{{< relref "post/2020-12-08-why-we-expect-group-differences-to-be-zero/index.en.markdown" >}}index.en_files/figure-html/unnamed-chunk-5-1.png" width="672" />







