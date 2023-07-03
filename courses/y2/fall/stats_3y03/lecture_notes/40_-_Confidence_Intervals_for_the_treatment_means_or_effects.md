---
title: 40 - Confidence Intervals for the treatment means or effects.md
description:
published: false
date: 2023-07-02 19:22:47.759216
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.759217
---

- Recall the treatment *means* are
$$\begin{aligned}
    \mu_i &= \mu + \tau_i
\end{aligned}$$
- we can $\mu_i$ by taking the sample mean across the treatment sample so
$$\begin{aligned}
    \hat \mu_i = \overline y_{i.} = \frac{\sum_{j=1}^n y_{ij}}{n}
\end{aligned}$$
- Recall that we have assumed linear statistical model, with $\epsilon_{ij} = N(0, \sigma^2)$
- Hence $\overline y_{i.} = \hat \mu_i = N(\mu_i, \frac{\sigma^2}{n})$

**We proceed as usual**:
- if we know $\sigma^2$ we can construct a $100(1 - \alpha)\%$ CI on $\mu_i$ as
$$\begin{aligned}
    \hat \mu_i \pm z_{\frac{\alpha}{2}} \left(\frac{\sigma}{\sqrt{n}}\right)
\end{aligned}$$
- If $\sigma^2$ is *unknown*, take the
$$\begin{aligned}
    ms_E
    &=
        \frac{\sum_{i=1}^a \sum_{j=1}^n (y_{ij} - \overline y_{i.})^2}{a(n-1)}
\end{aligned}$$
- Why? the variance of the error term $\sigma^2$ is assumed to be fixed across *all* samples $y_{ij}$ so by  taking $ms_E$ as an estimate for $\sigma^2$, we get a better estimate than we would just taking sample standard deviation of the treatment sample.
- In this take the test stat to be
$$\begin{aligned}
    T = \frac{\hat \mu_i - \mu_i}{\sqrt{\frac{ms_E}{n}}}
\end{aligned}$$
and then the CE (two-sided) is either $$\hat \mu_i \pm t_{\frac{\alpha}{2}, n-1}\sqrt{\frac{ms_E}{n}}$$ or
$$\begin{aligned}
    \hat \mu_i \pm z_{\frac{\alpha}{2}, n-1}\sqrt{\frac{ms_E}{n}}
\end{aligned}$$

**Similar**: comparing two treatment means
- given $\mu_{i_1}, \mu_{i_2}$ the means from two treatments, we want to compare.
$$\begin{aligned}
    Var(\overline Y_{i_1 .} - \overline Y_{i_2 .})
    &=
        Var(\hat \mu_{i_1 .} - \hat \mu_{i_2 .})
    \\&=
        \frac{\sigma^2}{n} + \frac{\sigma^2}{n}
    \\&=
        \frac{2\sigma^2}{n}
\end{aligned}$$

Same trick: estimate the mean difference

Get
$$\begin{aligned}
    T
    &=
        \frac{\hat \mu_{i_1} - \hat \mu_{i_2} - (\mu_{i_1} - \mu_{i_2})}{\sqrt{\frac{2ms_E}{n}}}
\end{aligned}$$
gives a CI
$$\begin{aligned}
    \hat \mu_{i_1} - \hat \mu_{i_2} \pm t_{\frac{\alpha}{2}, a(n-1)} \sqrt{\frac{2ms_E}{n}}
\end{aligned}$$

# Unbalanced Situation
- a treatments
- for treatment $i_j$ we have sample size $n_i$
- $N = \sum_{i=1}^a n_i \leftarrow$ total \# of samples across all treatments
- Let 
$$\begin{aligned}
    SS_T &= \sum_{i=1}^a \sum_{j=1}^{n_i} y_{ij}^2 - \frac{y_{..}^2}{N} 
    & & \text{\footnotesize($\frac{y_{..}^2}{N} = \overline y_{..}^2$)}\\ \\
    SS_{treat}
    &=
        \sum_{i=1}^a \frac{y_{i.}^2}{n_i} - \frac{y_{..}^2}{N}
    \\ \\
    SS_E
    &=
        SS_T - SS_{treat}
\end{aligned}$$

proceed as usual:
$$\begin{aligned}
    F_0 = \frac{SS_{treat}}{SS_{error}}
\end{aligned}$$

Reject $H_0$ if $f_0$ is too big. (equiv. if $\text{p-value} < \alpha$)

> ***Exam info***
> Fissure's LSD test will not be on the exam.

