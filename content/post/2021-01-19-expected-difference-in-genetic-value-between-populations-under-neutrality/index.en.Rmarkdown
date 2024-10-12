---
title: Expected difference in genetic value between populations under neutrality
author: admin
date: '2021-01-19'
draft: true
local: TRUE
slug: expected-difference-in-genetic-value-between-populations-under-neutrality
categories:
  - derivation
tags:
  - drift
  - genetic drift
  - quantitative genetics
  - genetic value
subtitle: ''
summary: ''
authors: []
lastmod: '2021-01-19T21:38:56-05:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

## Expected value of the phenotype in a population

Let $Y$ represent the phenotype of a randomly chosen individual from a randomly mating population. The expected value of $Y$ is $\mathbb{E}(Y) = 2 \beta f$ where $f$ is the frequency of the variant in the population and $\beta$ is its effect size. This can be derived using the law of total expectation:

$$\begin{aligned}
\mathbb{E}(Y) & = \mathbb{E} \{ \mathbb{E}(Y|X) \} \\
& = \mathbb{E}(Y|X = 0)P(X = 0) + \mathbb{E}(Y|X = 1)P(X = 1) + \mathbb{E}(Y|X = 2)P(X = 2) \\
& = 0(1-f)^2 + \beta2f(1-f) + 2\beta f^2 \\
& = 2\beta f - 2\beta f^2 + 2\beta f^2 \\
& = 2\beta f
\end{aligned}$$

Where $X$ is the number of the "effect" allele at the causal locus and $P(X = x)$ represents the frequency of the $x$ genotype in the population under random mating [^1]. We can easily extend this to the case where multiple causal variants underlie the phenotype: $\mathbb{E}(Y) = 2\sum_s \beta_s F_s$.

## Expected value of the difference in phenotype between populations

Now, let's think of two populations that diverged from a common ancestral population some $t$ generations ago. Let's denote the expected value of the phenotype in population 1 as $\mathbb{E}(Y_1) = 2 \beta F_{1}$ and in population 2 as $\mathbb{E}(Y_2) = 2 \beta F_{2}$. Note, that I'm assuming same effect size between populations. Then the expected value of the difference between the two populations is [^2]:

$$\begin{aligned}
\mathbb{E}(Y_1 - Y_2) =  \mathbb{E}(Y_1) - \mathbb{E}(Y_2) \\
= 2 \beta F_{1} - 2 \beta F_{2} = 2 \beta(F_{1} - F_{2})
\end{aligned}$$

Therefore, the expected difference in phenotype between the two populations really boils down to the difference in frequency between the two populations. Note, that the frequencies themselves are random variables, i.e. their realized values depend on a random evolutionary process - genetic drift (assuming no mutation or selection). So, to understand the expectation of the phenotypic difference between populations, we must derive the expectation of the difference in frequency ($\mathbb{E}(F_1 - F_2) = \mathbb{E}(F_1) - \mathbb{E}(F_2)$).

Now, assume that the frequency in the ancestral population was $f$ (known, not a random variable). Then we know that under genetic drift, the $\mathbb{E}(F_1) = \mathbb{E}(F_2) = f$. One way to come to this conclusion is through the Hardy-Weinberg principle, which states that in a large randomly mating population, the frequency of an allele remains constant across generations (in both populations after their split). 

Another way to think about this is if you think of population 1 sampling $2N_1$ alleles from the ancestral population. Then, each allele picked for population 1 is a bernoulli random variable with probability $f$ (the ancestral frequency) and the total number of alleles ($X_1$) sampled in population 1 is therefore a binomial random variable: $X_1 \sim Bin(N_1, f)$ with expectation $\mathbb{E}(X_1) = N_1 f$. And the expected frequency of the allele in the populaion is then $\frac{N_1f}{N_1} = f$. Similarly, if $N_2$ is the size of population 2, the frequency in population 2 is $\frac{N_2f}{N_2} = f$. Through induction, we can see that this result holds generation after generation. Thus, even $t$ generations after the split, $\mathbb{E}(F_1) = \mathbb{E}(F_2) = f$ and $\mathbb{E}(F_1 - F_2) = \mathbb{E}(F_1) - \mathbb{E}(F_2) = f - f = 0$. Thus, the expected difference in frequency between the two populations is expected to be zero and the expected difference in phenotype between the two populations is also, therefore, zero, i.e. $\mathbb{E}(Y_1 - Y_2) = \mathbb{E}\{ 2 \beta(F_{1} - F_{2})\} = 2\beta \mathbb{E}(F_1 - F_2) = 0$. This result is robust to model assumptions (e.g. distribution of frequency in ancestral population, population sizes etc.).

I used the example of one locus underlying the trait for illustration but this result can be extended to an arbitrary number of causal variants underlying the trait. Let's say now that we have $s$ causal variants, then the expected phenotypes are: $\mathbb{E}(Y_1) = \sum_s 2\beta_s F_{1,s}$ and $\mathbb{E}(Y_2) = \sum_s 2\beta_s F_{2,s}$ where $F_{1,s}$ is the frequency of the $s^{th}$ variant in population 1 and so on. And $\mathbb{E}(Y_1 - Y_2) = 2 \sum_s \beta_s \mathbb{E}(F_{1,s} - F_{2,s})$ is still zero because $\mathbb{E}(F_{1,s} - F_{2,s} = 0$ for each variant.



However, this does not mean that there will be no difference between the populations. Let me explain...

## Expectation of the genetic variance between populations




[^1]: Hard-Weinberg.
[^2]: From the linearity of expectations (see [this](https://en.wikipedia.org/wiki/Expected_value#Basic_properties) Wikipedia entry)



