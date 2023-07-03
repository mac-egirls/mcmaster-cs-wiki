---
title: 28 - One-sided confidence intervals.md
description:
published: false
date: 2023-07-02 19:22:47.754231
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.754245
---

2022-11-10

# One-sided confidence Bounds/Intervals
- Last time we phrased in terms of a bound, but we can also phrase in terms of some interval.

> ***Definition***
> Given some $\alpha \in (0, 1)$ and some parameter $\theta$
> 
> 1. An *upper* $100(1 - \alpha)\%$ CI for $\theta$, is an interval $(-\infty, U(X_1, \dots, X_n))$ s.t.
> $$\begin{aligned}
>     P(\theta \le U(X_1, \dots, X_n)) = 1 - \alpha
> \end{aligned}$$
> 2. A *lower* $100(1 - \alpha)\%$ CI for $\theta$ is an interval $(L(X_1, \dots, X_n), \infty)$ s.t
> $$\begin{aligned}
>     P(L(X_1, \dots, X_n) \le \theta) = 1 - \alpha
> \end{aligned}$$

If we are sampling a nofrmal distribution with known varriance $\sigma^2$, then (for the true mean $\mu$) a $100(1 - \alpha)\%$
- Upper CI is
$$\begin{aligned}
    \left(-\infty, \overline X + z_{\alpha} \frac{\sigma^2}{\sqrt{n}}\right)
\end{aligned}$$
- Lower $CI$ is
$$\begin{aligned}
    \left(\overline X - z_{\alpha} \frac{\sigma}{\sqrt{n}}, \infty\right)
\end{aligned}$$

##### Recall
$z_\alpha$ is the number s.t.
$$\begin{aligned}
    P(Z \le z_\alpha) = 1 - \alpha
\end{aligned}$$
$$P(Z \ge z_\gamma) = \gamma$$

![](/images/20230702002607.png)

When $\gamma = \frac{\alpha}{2}$

$$\begin{aligned}
    P\left(z \ge z_{\frac{\alpha}{2}}\right)= P\left(z \le -z_{\frac{\alpha}{2}}\right)= \frac{\alpha}{2}
\end{aligned}$$

#### Example
Distribution with $\gamma = 60$ and sample size is $36$
$$\begin{aligned}
    \alpha = 0.05 \leftrightsquigarrow \Phi(z_\alpha) &= 0.95 = 1 - \alpha \\
    z_\alpha &= 1.645
\end{aligned}$$

*So* the upper CI is
$$\begin{aligned}
    \left(-\infty, \overline X + (1.645)\left(\frac{60}{\sqrt{36}}\right)\right) &=
    \left(-\infty, \overline X + 16.45\right)
\end{aligned}$$

If take actual sample and compute $\overline X = 200$ then upper confidence bound is 216.45.

*Interpretation*: 95\% of the time if you sample the data repeatedly, the sample mean will be below $216.45$ $95\%$ of the time.

# Confidence Intervals for large sample size
- Imagine we want to give a CI for a distribution where we know $\sigma^2$, but not necessarily that the distribution is normal.
- By the *central limit theorem* if we know that $n$ is sufficiently large then the distribution of the sample mean is approximately normal.
$$\begin{aligned}
    \overline X \approx N\left(\mu, \frac{\sigma^2}{n}\right)
\end{aligned}$$
(even though $X$ may not have a normal distribution)

- If we know that $\overline X$ is normally distributed (approximately) the same algebra from last lecture applies.  *SO*
$$\begin{aligned}
    P\left(\overline X - z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{n}} \le \mu \le \overline X + z_\frac{\alpha}{2} \frac{\sigma}{\sqrt{n}}\right) &\approx 1 - \alpha
\end{aligned}$$

- What is sufficiently large?
    - $n \ge 30$  is usually good enough (lesht population distribution is very weird)

Suppose $\sigma$ is unknown.
- Let's estimate $\sigma^2$ with the sample variance $s^2$.
- For large enough sample size $n$ (typically $n \ge 40, 45$)
$$\begin{aligned}
    \frac{\overline X - \mu}{\frac{s}{\sqrt{n}}} &\approx N(0, 1) \\
    \overline X &\approx N\left(\mu, \frac{s^2}{n}\right)
\end{aligned}$$

*So* if we ware sampling a distribution with unknown mean and unknown variance, then a $100(1 - \alpha)\%$ CI on the mean of the population is
$$\begin{aligned}
    \left(\overline X - z_{\frac{\alpha}{2}} \frac{s}{\sqrt{n}}, \overline X + z_\frac{\alpha}{2} \frac{s}{\sqrt{n}}\right)
\end{aligned}$$
Provided $n$ is sufficiently large.