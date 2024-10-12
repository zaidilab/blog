---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Heritability (1): How 'genetic' is a trait?"
subtitle: ""
summary: ""
authors: [admin]
tags: [heritability, quantitative genetics]
categories: [main]
date: 2018-04-25T13:19:16-04:00
lastmod: 2018-04-25T13:19:16-04:00
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

One of the reasons I've come to write about this is because recently I've been asked a lot about "how genetic is this trait or that trait?". And I find myself responding with another question (yeah I'm that guy , get over it): "What do you mean by genetic?". I ask this because I think there is often a confusion between the term 'genetic' and 'heritable', and that distinction is extremely important to understand.

Maybe you've heard this before: Every trait is genetic. There are genes involved in the development of every trait. Nothing pops out of the environment (unless it's a spray tan or something?🤔). Is height genetic? Yes. Is hair color genetic? Yes. If you go work out a lot🏋🏽‍♂️, are your bulging biceps genetic? Yes, because there are genes that respond to the body's need by triggering a cascade of biochemical processes that result in muscle production. The question, "How genetic?", is not a legit question. What one really means to ask is "How heritable?".

Cutting to the chase and then I'll explain: **Heritability is the proportion of variation in a trait (Vp) explained by genetic differences among individuals (Vg).**

$$Heritability = \frac{V_g}{V_p}$$

$V_p = V_g + V_e$. This is the classic equation which, in english, reads: Variation in the phenotype/trait can be explained by the sum of the variation in the genotype ($V_g$) and variation in the environment ($V_e$), where environment is everything that is not 'genetic'. It becomes clear from the definition of heritability that it cannot be defined for a trait in a single individual. That's not a thing. It can only be defined for differences between two or more individuals.

Let's expand on this. Imagine there are 10 cows 🐮☘️ grazing on a pasture. They're all clones of each other, i.e., they are all exactly the same genetically. If you milk all of them, the milk yield 🥛 will vary among them (Figure 1). How much it varies (the variance) is Vp. Is the milk yield of a cow genetic? There are genes involved in milk production, so yeah. Is the milk yield among the cows heritable? Nope. Think about it. Since the cows are clones of one another, there are no genetic differences among them (i.e. $V_g = 0$ 👌🏽) . So any differences in milk yield have to be because of the environment ($V_p = V_e$). Maybe they were grazing on different regions of the pasture or maybe some of them were being tipped more than others 🙌🐄 (it's a real thing). The heritability of milk yield among the cows is 0.


![cows](/media/heritability1/herit1-01.jpg)
*Figure 1: Variation in milk yield in a hypothetical herd of cloned cows. Since there is no genetic variation among cows, heritability of milk production in THIS set of cows is zero.*

There are some other things about the concept of heritability that make it tricky. One thing that I'll mention now and leave the rest for some other time is that heritability is not a fundamental property of the trait itself. It is context specific and is a property of the sample you are looking at. If I tried to measure the heritability of milk yield in another set of 10 cows grazing in the same pasture, who are genetically different from one another, the heritability of milk yield will likely not be zero since $V_g > 0$.

So when most people ask "how genetic is skin pigmentation" or "how genetic is intelligence" (that's a whole can of worms that I hope to address at some point), they're really asking "how heritable are they?".

![meme](/media/heritability1/meme.jpg)
