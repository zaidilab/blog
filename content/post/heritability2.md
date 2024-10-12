---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Heritability (2): narrow and broad sense heritability"
subtitle: ""
summary: ""
authors: [admin]
tags: [heritability, quantitative genetics]
categories: [main]
date: 2018-05-04T16:24:08-04:00
lastmod: 2018-05-04T16:24:08-04:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Quick recap: I mentioned last time that heritability = Vg / Vp, where Vg is the genetic variance among individuals and Vp is the total phenotypic difference among individuals. Furthermore, Vp = Vg + Ve, where Ve is the environmental variance contributing to phenotypic differences.

There are two different types of heritability: broad-sense heritability and narrow-sense heritability. What we've been discussing so far is broad-sense heritability: the proportion of phenotypic variance that can be explained by ALL genetic differences among individuals. Geneticists often like to split Vg, the genetic variance, into two: additive genetic variance and non-additive genetic variance. There is a reason for this split (besides a masochistic need to make life harder for everyone 🤦🏽‍♂️), which I will talk about later but first let's talk about what these things are.

Additive genetic variance first since that's easier. Suppose there is a gene called A (very creative, I know 😛) involved in milk production in cows 🐮. Further suppose that a cow can have the genotype AA, Aa, or aa at gene A because cows are diploid. Cows with genotype aa produce, on average, 10 liters of milk everyday. I don't know if that's a normal amount or not so don't judge me if you're a farmer 👨🏻‍🌾 and you've chanced upon this blog. Cows with a single A allele in their genotype (i.e. genotype Aa or aA) produce, on average, 20 liters of milk and cows with genotype AA produce 30 (Fig. 1).

![cows](/media/heritability2/herit-2-01.jpg)
**Figure 1:** Cows with different genotypes can have different means for milk yield. This variation is due to a combination of genetic and environmental differences. However, among cows with the same genotype, differences in milk yield are purely due to environmental differences.
There are a couple of interesting things happening here (if we play fast and loose with the word 'interesting'😅)

There are differences in milk yield among cows of the same genotype even though there are no genetic differences among them (Vg = 0) (Fig. 1). Remember from the last post that these differences arise solely because of environmental differences. This is why I keep saying things like "cows with a single A allele produce, on average, 20 liters of milk" as there are some that might produce 22 and some that might produce 18, because of small environmental differences. Note also that this means that heritability among cows of the same genotype is 0. Ok, I think I've hammered 🔨 this point hard enough.
The differences among groups of cows with different genotypes (AA vs Aa vs aa) arise not only due to environmental differences, but also due to genetic differences (i.e. Vg > 0). Because Vg > 0, Heritability > 0 and we can say that milk yield is heritable in this specific herd of cows (Fig. 1).

It seems that each additional A allele that a cow carries, on average, increases the milk production by 10 liters (aa = 10, Aa = 20, AA = 30, Fig. 1). There is no dominant or recessive allele, despite my poor use of the letters. We say that the effect of A (and a if we look at it as decreasing milk yield) is additive. If one of the alleles were dominant/recessive, we would say the allelic effects are non-additive because we couldn't just figure out the average milk yield by adding up the number of A alleles. (Side exercise: if A is the dominant allele and a is recessive, what would the average milk yields be for the three genotypes?).

The last point can be extended from one gene/ locus to two (or more) genes/loci. Different alleles at the two loci might contribute additively to milk yield (Fig. 2). This additivity has everything to do with the difference between narrow-sense and broad-sense heritability. If broad-sense heritability is the proportion of phenotypic variance that is due to ALL genetic effects (additive + non-additive), narrow-sense heritability is the proportion of phenotypic variation only due to additive genetic effects. What are non-additive effects? Why are they important? Why does this distinction matter? What is the meaning of life 🌄🤔? There's a whole post about this (ok, not the last question), so stay tuned 😎🍿.

![cows](/media/heritability2/herit2_punnett-01.jpg)
**Figure 2:** The effect of alleles on milk yield (numbers) in this example is additive. Doesn't matter if we look at each gene separately, or combine effects across them.
Primary source: Lynch M, Walsh B. 1998. Genetics and analysis of quantitative traits. Sunderland, MA: Sinauer Associates, Inc.
