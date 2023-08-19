---
title: 32 - Hypotehesis Testing.md
description:
published: false
date: 2023-07-02 19:22:47.759019
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.759021
---

2022-11-15
*Idea*: Test statistical hypothesis

# Setup
$H_0$ *(aka the null hypothesis)* a statement about a parameter *which we assume to be true*.

#### Example
$H_0$: the average height of 3rd year end students is 6'5"
$H_1$ (aka the alternative hypothesis): a statement which directly contradicts $H_0$
> ***Note***
> $H_1$ not necessarily the negation of $H_0$
> - $H_1$: the mean height is not 6'5" (two-tailed test/two-sided test)
> - $H_1$: the mean height is <6'5" (lower one-tailed/one-sided test)
> - $H_1$: the mean height is >6'5" (upper one-tailed/one-sided test)

# General Strategy of a Basic Hypothesis Test
- Assume $H_0$ is true.
- Sample some 
    - *Question*: Do we observe sometimes that something it is very unlikely *given* that $H_0$ is true?
    - If *yes*, reject $H_0$ in favour of $H_1$.
    - If *no*, accept $H_0$ based on the evidence.

1. Choose a reasonable statistic for estimating $\theta$, say $\hat \Theta$.
2. Choose a *critical region*
    - A region $R$ (for us $R$ will always be an interval) such that given a sample $x_1, \dots, x_n$ and a point estimate $\hat \theta = \hat \Theta(x_1, \dots, x_n)$ *then*
        - If $\hat \theta \in R$, accept $H_0$ based on the evidence.
        - If $\hat \theta \notin R$, reject $H_0$ in favour of $H_1$.

> ***philosophical thought***
> Accepting $H_0$ is not asserting that $H_0$ is true, it just saying that there is not enough evidence to suggest that $H_0$ is unlikely to be true.

#### Example
you work for Nestle (you are evil *😩*). They tell you that the volume of water bottles coming from a certain factory is normally distributed with $\mu = 100ml$, $\sigma = 5ml$.

You want to test if this is true.
$$\begin{aligned}
    H_0&: \mu = 100 ml \\
    H_1&: \mu \ne 100ml (\text{two-sided test})
\end{aligned}$$

##### Q1
We take a sample of 1000 bottles and find a sample average volume $\overline x = 90ml$. *Should we accept or reject $H_0$?*
If $H_0$ is *true*, then
$$\begin{aligned}
    \overline X \sim N\left(100 , \frac{5^2}{1000}\right)
\end{aligned}$$

*Ask*:
$$\begin{aligned}
    P(\overline X \le 90)
    &=
        P\left(Z \le \frac{90 - 100}{\frac{5}{\sqrt{1000}}}\right)
    \\&=
        P(Z \le -63.25)
    \\&\approx
        0
\end{aligned}$$

![](/images/20230702003924.png)
- Extremely unlikely
- So we probably should reject $H_0$ in favour of $H_1$.

##### Q2
Take a sample, compute $\overline x$. The following is a graph of $\overline x$

![](/images/20230702003951.png)
- Choosing $R$ depends on estimator for $\theta$.

# Possible outcomes for HT
| N/A          | $H_0$ is true | $H_0$ is false |
| ------------ | ------------- | -------------- |
| Accept $H_0$ | yay           | type II ERROR  | 
| Accept $H_1$ | Type I ERROR  | yay            |

> ***Exam Info***
> Type II errors are not on the test

> ***Define***
> $$\begin{aligned}
>     \alpha &= P(\text{Type II ERROR}) \\
>     &= P(\text{Probability of rejecting $H_0$ | $H_0$ is true})
> \end{aligned}$$
> 
> $\alpha$ is called the "significance level" of the test.
> 
> $$\begin{aligned}
>     \beta = P(\text{Type II ERROR})
> \end{aligned}$$
> 
> $1 - \beta$ is the "power" of the test.

#### Exercise
Suppose a normal distribution with $\sigma = 10, n = 35$.
Consider the test
$$\begin{aligned}
    H_0&: \mu = 50 \\
    H_1&: \mu \ne 50
\end{aligned}$$

Suppose the CR is
$$\begin{aligned}
    (48, 52)
\end{aligned}$$
- $\overline X =$ sample statistic.
Find $\alpha$.
$$\begin{aligned}
    \alpha &= P(\text{Probability of rejecting $H_0$ | $H_0$ is true})
\end{aligned}$$
Suppose $H_0$ is true, *then*
$$\begin{aligned}
    \overline X \sim N\left(50, \frac{100}{35}\right)
\end{aligned}$$

Reject $H_0$ iff $\overline X$ is outside my $CR$.
$$\begin{aligned}
    \alpha &= P(\overline X \ge 52) + P(\overline X \le 48)
    \\&\approx 0.238
\end{aligned}$$
