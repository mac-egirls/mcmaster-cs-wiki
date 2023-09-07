---
title: 35  - tests or CI on the difference of two means of normal distributions with variance unknown.md
description: 
published: true
date: 2023-07-03T00:29:17.074Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:29:12.567Z
---

# Testing
- we imagine that we are sampling two normal dist. $N(\mu_1, \sigma_1^2)$ and $N(\mu_2, \sigma_2^2)$ where $\mu_1, \mu_2, \sigma_1^2, \sigma_2^2$ are unknown.
- let's assume we take $n_1$ samples from $N(\mu_1, \sigma_1^2)$ and $n_2$ samples from $N(\mu_2, \sigma_2^2)$
- $n_1$ and $n_2$ are not necessarily equal.
- set up a hypothesis test to see their difference $\mu_1 - \mu_2$.

## Test Setup
$$\begin{aligned}
    H_0&: \mu_1 - \mu_2 = \triangle_0 \\
    H_1&: \mu_1 - \mu_2 \ne \triangle_0 \lor \mu_1 - \mu_2 > \triangle_0 \lor \mu_1 - \mu_2 < \triangle_0
\end{aligned}$$
- Let $\overline{X_i}$ is the sample mean from the sample taken from $N(\mu_i, \sigma_i^2)$.
    - then $\overline{X_i} \sim N(\mu_i, \frac{\sigma_i^2}{n})$
    - *So* $\overline{X_1} - \overline X_2 \sim N\left(\mu_1 - \mu_2, \frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}\right)$

We can consider two cases
1. $\sigma_1^2 = \sigma_2^2 = \sigma^2$ (same but unknown)
2. $\sigma_1^2 \ne \sigma_2^2$

### Case 1: $\sigma_1^2 = \sigma_2^2 = \sigma^2$
$$\begin{aligned}
    \overline X_1 - \overline X_2 \sim N\left(\mu_1 - \mu_2, \sigma^2\left(\frac{n_1+n_2}{n_1n_2}\right)\right)
\end{aligned}$$
- $\sigma_2$ is unknown, so we want to estimate it.
    - We have estimator for $\sigma^2$ from sample 1, $s_1^2$
    - also have estimator for $\sigma^2$ from sample 2, $s_2^2$
    - average to get a pooled estimator
$$\begin{aligned}
    s_p^2 &= \frac{(n_1-1)s_1^2 + (n_2-1)s_2^2}{n_1+n_2-2}
    \\&= \left(\frac{n_1-1}{n_1+n_2-2}\right)s_1^2 +
        \left(\frac{n_2-1}{n_1+n_2-2}\right)s_2^2
\end{aligned}$$

> ***note***
> Let $w$ and $1-w$ be the corresponding coefficients to the sample variances.
> 
> $$\begin{aligned}
>     E[s_p^2] &= wE[S_1^2] + (1 - w)E[s_2^2] \\
>     &=
>         w \sigma^2 + (1-w)\sigma^2
>     \\&=
>         (1 - w+w) \sigma^2
>     \\&=
>         \sigma^2
> \end{aligned}$$

- we now want to choose a test statistic
    - either $Z$ or $T$ stat (depending on $n$)
$$\begin{aligned}
    T_0 &=
        \frac{(\overline X_1 - \overline X_2) - \triangle_0}{s_p\sqrt{\frac{n_1+n_2}{n_1n_2}}}
\end{aligned}$$
- has a $t$-distribution with $n_1 + n_2 - 2$ degrees of freedom, assuming $H_0$ is true.

*Proceed wtih a $t$-test as usual (OR $z$-test if confidence that $n_1$ and $n_2$ are big enough)*

### Case 2: $\sigma_1^2 \ne \sigma_2^2$
- We still have $s_1^2$ an estimate for $\sigma_1^2$ and $s_2^2$ an estimate for $\sigma_2^2$, but $\sigma_1^2 \ne \sigma_2^2$ so we *should not* pool them.
- take
$$\begin{aligned}
    T_0 &=
        \frac{(\overline X_1 - \overline X_2) - \triangle_0}{\sqrt{\frac{s_1^2}{n_1}+ \frac{s_2^2}{n_2}}}
\end{aligned}$$

*Then* $H_0$ is true *iff* $T_0$ has a $t$-distribution with $\nu$ degrees of freedom where
$$\begin{aligned}
    \nu &=
        \left\lfloor \dfrac{\left(\dfrac{s_1^2}{n_1} + \dfrac{s_2^2}{n_2}\right)^2}{\dfrac{\left(\dfrac{s_1^2}{n_1}\right)^2}{n_1-1} + \dfrac{\left(\dfrac{s_2^2}{n_2}\right)^2}{n_2-1}} \right\rfloor
\end{aligned}$$

> ***Remark***
> $t$-tests are extremenetly sensitive to pooled variances if you aren't really sure that $\sigma_1^2 = \sigma_2^2$ you should use case 2.

![](/images/20221208105003.png)

# Tests on difference in means, variance known
![](/images/20221208104552.png)
