---
title: 26 - ch8 - statistical intervals.md
description:
published: false
date: 2023-07-02 19:22:47.756496
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.756497
---

# Confidence Interval
- Suppose $\hat \Theta$ is an estimator for some parameters
- Given a sample of data $\{x_1, \dots, x_n\} \subseteq \mathbb{R}$
    - Get a point estimate for $\theta$
$$\begin{aligned}
    \hat \theta = \hat \Theta(x_1, \dots, x_n)
\end{aligned}$$

- *Goal*: give some estimate/certainty of how close $\hat \theta$ is to $\theta$.
    - At the very least, sample repeatedly and try to find an interval in which our point estimates are likely to appear.

> ***Definition of Confidence Interval***
> A $100(1- \alpha) \%$ ***confidence interval*** for $\theta$ is a random interval
> $$\begin{aligned}
>     [L(X_1, \dots, X_n), U(X_1, \dots, X_n)]
> \end{aligned}$$
> such that
> $$\begin{aligned}
>     P(L(X_1, \dots, X_n) \le \theta \le U(X_1, \dots, X_n)) = 1 - \alpha
> \end{aligned}$$
> - This is super dependent on the distribution of $\hat \Theta(X_1, \dots, X_n)$

##### Remark on terminology
The parameter $\alpha \in (0, 1)$ is such that $1 - \alpha$ is called the confidence.
- *You*, the statistician, chooses the $\alpha$.
$$\begin{aligned}
    \alpha &= 0.1  & & \text{\footnotesize(90\% confidence)}\\
    \alpha &= 0.05  & & \text{\footnotesize(95\% confidence)}\\
    \alpha &= 0.01  & & \text{\footnotesize(99\% confidence)}\\
\end{aligned}$$

##### Interpretation
If we sample may their and compute the corresponding point estimates, they would fall into the CI $100(1- \alpha) \%$ of the time.




