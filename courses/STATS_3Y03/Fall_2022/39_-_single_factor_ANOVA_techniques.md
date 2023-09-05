---
title: 39 - single factor ANOVA techniques.md
description: 
published: true
date: 2023-07-10T21:21:58.454Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:29:33.914Z
---

- We have an experiment where we vary a single factor (expel dosage, temperature, true, etc.)
- We assume finitely many values for the varying factor (called the treatments)
    - *e.x.* low, med, high dose of some drug
- Assume $a \in \mathbb{N}$ many treatments
    - for each treatment, $n_i$ many random samples of the form

$$\begin{aligned}
    Y_{ij} = \mu + \tau_i + \epsilon_{ij}
\end{aligned}$$
- $1 \le i \le a, 1 \le j \le n_i$
- $\mu$ - some fixed mean
- $\tau_j$ - some parameter
- $\epsilon_{i_j}$ some noise random variable.
- Simplifying assumptions:
    1. *Balanced test*: $n_i = n$, all samples same size
    2. *Assume* $\sum_{i=1}^a \tau_i = 0$
- Second assumptions allows us to test the hypothesis

$$\begin{aligned}
    H_0&: \tau_1 = \tau_2 = \dots = \tau_a = 0 \\
    H_1&: \text{ there is at least one $i$ such that $\tau_i \ne 0$}
\end{aligned}$$


We now sample some data:
$$\begin{aligned}
    \{y_{ij}: 1 \le i \le a, 1 \le j \le n \}
\end{aligned}$$
- $a$ - number of treatments
- $n$ - sample size per treatment

**ANOVA Equation** (A decomposition of the variation)
$$\begin{aligned}
    \sum_{i=1}^a \sum_{j=1}^n(y_{ij} - \overline y_{..})^2
    &=
        n \sum_{i=1}^a(y_{i.} - \overline y_{..})^2
        +
        \sum_{i=1}^a \sum_{j=1}^n (y_{ij} - \overline y_{i.})^2
\end{aligned}$$
- $\overline y_{..}$ - sample average of all samples
- $\overline y_{i.}$ - treatment mean, the average of all samples in treatment $i$.
- First term is *$SS_T$*, Second term is *$SS_{Treatments}$*, Third term is *$SS_{E}$*, an estimate for $\sigma^2$
- We want to build some sort of statistic. 

> ***Single Factor with Equal Sample Sizes***
> The sum of squares computing formulas for the ANOVA with equal sample sizes in each treatment are
> 
> $$\begin{aligned}
>     SS_T&=
>         \sum_{i=1}^a
>         \sum_{j=1}^n
>         y_{ij}^2 - \frac{y_{..}^2}{N} \\
>     SS_{treatments}
>     &=
>         \sum_{i=1}^a \frac{y_{i.}^2}{n} - \frac{y_{..}^2}{N}
>     \\ \\
>     SS_E
>     &=
>         SS_T - SS_{treatments}
>     \\&=
>         \sum_{i=1}^a\sum_{j=1}^n\left(y_{ij} - \frac{y_{i.}}{n}\right)^2
>     \\&=
>         \sum_{i=1}^a
>         \sum_{j=1}^n
>         y_{ij}^2 - \sum_{i=1}^a \frac{y_{i.}^2}{n}
> \end{aligned}$$
> 
> - $SS_E$ - sum of squares within groups
> - $SS_{treatments}$ - sum of squares between groups
> - $SS_T$ - total sum of squares

Visually, $SS_T = SS_{treatments} + SS_E$ is
![](/images/20221209130502.png)


> ***Define***
> $$\begin{aligned}
>     F_0
>     &=
>         \frac{SS_{\text{treat} / a-1}}{SS_{E / a(n-1)}}
>     \\&:=
>         \frac{mS_{treat}}{mS_E}
> \end{aligned}$$
- $mS_{treat}$ - mean squared treatment
- $mS_{E}$ - mean squared error

> ***Idea***
> If a lot of variation is "explained by/captured by" the treatment effects, i.e. if the portion of the total variation coming from the treatments is high compared to the "noise" variatino of the error term, then we should reject $H_0$.

> ***Fact***
> - A ratio of mean squares always is distributed like an $f$-random variable.
> - $f$ random variables are new!
>     - two-parameter family of RV's.
>         - They are parameterized by the degrees of freedom of hte numerator and degrees of freedom of denominator

- In our case, our $f$ statistic should be of the form
$$\begin{aligned}
    f_{\alpha, a-1, a(n-1)}
\end{aligned}$$
- So the ANOVA test should result in a rejection of $H_0$ *iff* we detect too high of a value for our statistic.
- Let's fix a confidence level $1 - \alpha$.
    - Let $f_{\alpha, a - 1, a(n-1)}$ be the value such that
$$\begin{aligned}
    P(F_0 > f_{\alpha, a - 1, a(n-1)})
    =
        \alpha
\end{aligned}$$

![](/images/20230701105849.png)
- \* - $f_{\alpha, a-1, a(n-1)}$
If our value $f_0$ of $F_0$ is too big, i.e., $f_0 > f_{\alpha, a - 1, a(n-1)}$ then reject $H_0$.

> ***Could be on the exam***
> | Source of variation | sum of squares | degrees of freedom | mean square                           | $F_0$                     |
> | ------------------- | -------------- | ------------------ | ------------------------------------- | ------------------------- |
> | treat               | $SS_{treat}$   | $a-1$              | $mS_{treat} = \frac{SS_{treat}}{a-1}$ | $\frac{mS_{treat}}{mS_E}$ |
> | error               | $SS_E$         | $N - a$            | $mS_E = \frac{SS_{E}}{a(n-1)}$        |                           |
> | total               | $SS_{total}$   | $N-1$              |                                       |                           |
