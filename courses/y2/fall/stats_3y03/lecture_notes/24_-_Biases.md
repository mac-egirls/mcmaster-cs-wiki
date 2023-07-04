---
title: 24 - Biases.md
description:
published: false
date: 2023-07-03 00:49:52.992842
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.992844
---

- A random sample is $(X_1, \cdots, X_n)$ as iid (*independent and identically distributed*) sequence of RV's
- A statistic is any function $\Theta(X_1, \cdots, X_n)$
    - Also an $RV$ with its own distribution
- [Central Limit Theorem](/courses/y2/fall/stats_3y03/lecture_notes/24_-_Biases.md): $\overline X = \frac{1}{n}(X_1 + \cdots + X_n)$ tends to a [Normal Distribution](/courses/y2/fall/stats_3y03/lecture_notes/24_-_Biases.md) as $n$ gets large.
- More specifically: if $E[X_i] = \mu$, $Var(X_i) = \sigma^2$, then $\overline X \approx N(\mu, \frac{\sigma^2}{n})$.

#### Example
An electricity company manufactures resistors and they have a mean resistance of 100 $\ohm$ with a standard dev. of $10 \ohm$. If the resistance is normally distributed, what is the probability that a sample of 25 has an average resistance of $\le 95 \ohm$?

##### Solution
$\overline X =$ the average resistance for the 25 samples. Then $\overline X \sim N\left(100, \frac{10^2}{25}\right)= N(100, 4)$. So we want
$$\begin{aligned}
    P(\overline X \le 95)
    &=
        P(Z \le \frac{95-100}{2})
    \\&=
        P(Z \le -2.5)
    \\&=
        \Phi(-2.5)
    \\&\approx
        0.0062
\end{aligned}$$

##### Remark
If you actually did this, what is more likely:
1. The true mean is not $100 \ohm$
2. You got very lucky with your random sample.

#### [Recall](/courses/y2/fall/stats_3y03/lecture_notes/24_-_Biases.md)
If $\theta$ is a parameter for a distribution, then a statistic used to estimate $\theta$ is called an estimator.
- Median is an estimator for $\mu$
- $n\%$-trimmed mean
    - (trim off the upper and lower $n\%$) of your sample and compute average) also an estimator for $\mu$.
- $\frac{IQR}{2}+q_1$ is also an estimator for $\mu$

# Bias
> ***Bias***
> Suppose $\theta$ is a parameter and $\hat \Theta$ is an estimator for $\theta$. We define the Bias of $\hat \Theta$ to be
> $$\begin{aligned}
>     Bias(\hat \Theta)
>     &=
>         E[\hat \Theta - \theta]
>     \\&=
>         E[\hat \Theta] - \theta
> \end{aligned}$$
> 
> We say $\hat \Theta$ is *unbiased* if $Bias (\hat \Theta) = 0$

#### Example
$(X_1, \dots, X_n)$ is a random sample with mean $\mu$, variance $\sigma^2$. Then,
$$\begin{aligned}
    E[\overline X] &= E\left[\frac{1}{n}(X_1 + \cdots + X_n)\right]
    \\&=
        \frac{1}{n} \sum_{i=1}^n E[X_i]
    \\&=
        \frac{n \mu}{n} 
    \\&= 
        \mu
\end{aligned}$$

So $\overline X$ is an unbiased estimator of $\mu$.

## Claim:
$s^2$ (***sample variance***) is an unbiased estimator of $\sigma^2$
$$\begin{aligned}
    E[s^2]
    &=
        E\left[\frac{\sum_{i=1}^n (X_i - \overline X)^2}{n-1}\right]
    \\&=
        E\left[\frac{\sum_{i=1}^n (X_i + \overline X^2 - 2 \overline X X_i)}{n-1}\right]
    \\&=
        E\left[\frac{\sum_{i=1}^n X_i^2 - n\overline X^2}{n-1}\right]
    \\&=
        \frac{1}{n-1} \left( \sum_{i=1}^n E[X_i^2] - nE[\overline X^2] \right)
    \\&=
        \frac{1}{n-1} \left( \sum_{i=1}^n \left(\sigma^2 + \mu^2\right) - n\left(\frac{\sigma^2}{n}+ \mu^2\right) \right)
    \\&=
        \frac{1}{n-1} \left( n(\sigma^2 + \mu^2) - \sigma^2 - n\mu^2) \right)
    \\&=
        \frac{1}{n-1} \left( n \sigma^2 - \sigma^2 \right)
    \\&=
        \frac{1}{n-1} \left( \sigma^2(n - 1\right))
    \\&=
        \sigma^2
\end{aligned}$$

This answers why we define
$$\begin{aligned}
    S^2 &= \frac{1}{n-1} \sum_{i=1}^n (X_i - \overline X)^2
    \text{ and not }
    \frac{1}{n} \sum_{i=1}^n (X_i - \overline X)^2
\end{aligned}$$

#### Remark
$$\begin{aligned}
    Bias\left(\frac{1}{n} \sum_{i=1}^n (X_i - \overline X)^2\right)
    &=
        \frac{n-1}{n} \sigma^2 - \sigma^2
    \\&=
        \sigma^2 \left(\frac{n-1}{n} - 1\right)
    \\&\to 0 \text{ as } n \to \infty
\end{aligned}$$

