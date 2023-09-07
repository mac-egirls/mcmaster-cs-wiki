---
title: 27 - confidence intervals.md
description: 
published: true
date: 2023-09-05T18:08:20.991Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:28:30.018Z
---

2022-11-08

# [Last Time](/courses/y2/fall/stats_3y03/lecture_notes/27_-_confidence_intervals.md)
- Suppose we have an estimator $\Theta$ to some parameter $\theta$.
- We take a sample of data $x_1, \dots, x_n$
    - $\hat \Theta(x_1, \dots, x_n) = \hat \theta$ is a point estimate.
- A $100(1 - \alpha)\%$ CI for $\theta$ is a Random Interval
$$[L(X_1, \dots, X_n), U(X_1, \dots, X_n)]$$ such that
$$P(L(X_1, \dots, X_n) \le \theta \le U(X_1, \dots, X_n)) = 1 - \alpha$$
- with $\theta$ the true parameter.

# Today
First approach case: sampling a normal distribution with known $\sigma$.
- We want to construct a CI for $\mu = E[X]$  where $x \sim N(\mu, \sigma^2)$ and we know $\sigma^2$.
- Let's take $\overline X$ to be the estimator for $\mu$.
- Since we know the population we are sampling is normal with variance $\sigma^2$, we know that $\overline X \sim N(\mu, \frac{\sigma^2}{n})$
    - $\mu$ - unknown
    - $\frac{\sigma^2}{n}$ - known
- We can standardize
$$Z = \frac{\overline X - \mu}{\frac{\sigma}{\sqrt{n}}}$$
- Suppose we want a $100(1 - \alpha)\%$ CI.
- Find a value $z_{\frac{\alpha}{2}}$ Such that
$$\begin{aligned}
    P\left(-z_{\frac{\alpha}{2}} \le z \le z_{\frac{\alpha}{2}}\right)&= 1 - \alpha \\
    \Phi\left(-z_{\frac{\alpha}{2}}\right)&= \frac{\alpha}{2} \\
    -z_{\frac{\alpha}{2}} &= \Phi^{-1}\left(\frac{\alpha}{2}\right)
\end{aligned}$$

Given such a $z_{\alpha_2}$ have
$$\begin{aligned}
    P\left(-z_{\frac{\alpha}{2}} \le \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{n}}} \le z_{\frac{\alpha}{2}}\right)&= 1 - \alpha \\
    P\left(-z_{\frac{\alpha}{2}} \ \cdot \frac{\sigma}{\sqrt{n}} \le \overline X-\mu \le z_{\frac{\alpha}{2}} \cdot \frac{\sigma}{\sqrt{n}}\right)&= 1 - \alpha \\
    P\left(\overline X -z_{\frac{\alpha}{2}} \ \cdot \frac{\sigma}{\sqrt{n}} \le \overline \mu \le \overline X + z_{\frac{\alpha}{2}} \cdot \frac{\sigma}{\sqrt{n}}\right)&= 1 - \alpha \\
\end{aligned}$$
So
![](/images/20221120121614.png)

If take actual data $x_1, \dots, x_n$, then
$$
    \left[\overline X -z_{\frac{\alpha}{2}} \ \cdot \frac{\sigma}{\sqrt{n}} , \overline X + z_{\frac{\alpha}{2}} \cdot \frac{\sigma}{\sqrt{n}}\right] \\
$$
Is actually the real interval
- tradeoff small range for certainty

##### Remark
As $\alpha \to 0$ (i.e., as confidence $1 - \alpha \to 1$), CT must get bigger (not always useful)
- The length of the interval $wE$ is called the precision of the CI.

#### Example
Suppose we want a $95\%$ CI for a normal distribution with $\sigma = 60$ and n = 36 sample size.

#### Solution
$100(1 - \alpha) = 95$, $1 - \alpha = 0.95$ so $\alpha = 0.05$.

Want $z_{\frac{\alpha}{2}}$, so by definition $z_{\frac{\alpha}{2}}$ is such that
$$\begin{aligned}
    P\left(Z \le - z_\frac{\alpha}{2}\right) &= P\left(Z \ge z_{\frac{\alpha}{2}}\right)
    \\&= \frac{\alpha}{2} 
    \\&= 0.025
\end{aligned}$$
Go to tables: $z_{\frac{\alpha}{2}} = 1.96$

So the margin of error is
$$\begin{aligned}
    E &= z_{\frac{\alpha}{2}} \cdot \frac{\sigma}{\sqrt{n}}
    \\&=
        (1.96) \frac{60}{6}
    \\&=
        19.6
\end{aligned}$$

Say we collect some data and find $\overline x = 200$, then our $95\%$ CI on the true mean $\mu$, is
$$\begin{aligned}
    [180.4, 219.6]
\end{aligned}$$

> ***Margin of Error***
> If have confidence interval $[\alpha, \beta]$, then the margin of error $E$ is
> $$\begin{aligned}
>     E = \frac{\beta - \alpha}{2}
> \end{aligned}$$


# Choosing Sample size
> ***Choose upper bound***
> Know error of $100(1 - \alpha)\%$ CI on $\mu$ with known $\sigma$ is $E = Z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{n}}$
> If want to have upper bound on error chosen s.t.
> $$\begin{aligned}
>     n \ge \left(\frac{Z_{\frac{\alpha}{2}} \sigma}{E}\right)^2
> \end{aligned}$$

#### Example
Suppose sampling normal distribution with $\sigma = 60$ what sample size is needed to guarantee a $95\%$ CI with precision 20 (i.e., E = 10)

$$\begin{aligned}
    Z_{\frac{\alpha}{2}} = 1.96, n > \left(\frac{(1.96)(60)}{10}\right)^2 \approx 136
\end{aligned}$$

but, if we wanted to shrink the precision to 10, then
$$\begin{aligned}
    n > 
     \left(\frac{(1.96)(60)}{5}\right)^2 \approx 553
\end{aligned}$$

# one-sided confidence bounds
- One sided CI's show up when you don't care about hte bounds
- We obtain one-sided bounds by letting either $L = -\infty$ or $U = \infty$
- Also, replace $z_{\frac{\alpha}{2}}$, with $z_\alpha$ where $z_\alpha$ is such that
$$\begin{aligned}
    P(Z \le -z_{\alpha}) = P(z \ge z_{\alpha_2}) = \alpha
\end{aligned}$$

Reasoning the same
- A $100(1 - \alpha\%)$ *upper* CI on $\mu$ is
$$\begin{aligned}
    \mu \le \overline x + z_\alpha \cdot \frac{\sigma}{\sqrt{n}}
\end{aligned}$$

- A $100(1 - \alpha)\%$ lower confidence bound on $\mu$ is
$$\overline x - z_\alpha \frac{\alpha}{\sqrt{n}} \le \mu$$
