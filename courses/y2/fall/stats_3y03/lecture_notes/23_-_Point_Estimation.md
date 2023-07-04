---
title: 23 - Point Estimation.md
description:
published: false
date: 2023-07-03 00:49:52.992385
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.992387
---

- ***parameter*** - any numerical property/feature of a distribution.

> ***Def. of a Statistic***
> A *statistic* is a function of a random sample, $h(X_1, \dots, X_n)$

Suppose $\theta$ is a parameter of a variable $X$, and $X_1, \dots, X_n$ is a random sample of a distribution of $X$, we say
$$\begin{aligned}
    \hat \Theta &= h (X_1, \dots, X_n)
\end{aligned}$$
is a ***point estimator*** for $\theta$ if we use it to estimate $\theta$. 
- $\hat \Theta$ is a random variable since it's a function of random variables.

#### Example
$\overline X$ can be used to estimate $$E[X] = \mu$$
- for *example*: there are is some average height $\mu$ of all $3^{rd}$ year engineers (which is unknown). But we can take a random sample of 20 $3^{rd}$ year engineers and take the sample mean to get an estimate for $\mu$.

- Suppose $\hat \Theta(X_1, \dots, X_n)$ is an estimator for $\theta$ and $(x_1, \dots, x_n) \in \mathbb{R}^n$ is a sample of data. Then $$\hat \theta = \hat \Theta(x_1, \dots, x_n) \in \mathbb{R}$$ is called a ***point estimate*** of $\theta$.

- ***Sampling Distribution*** - the probability distribution of $\hat \Theta$

# Central Limit Theorem
Suppose $X_1, X_2, \dots$ is iid (independent, identically distributed). with mean $E[X_i] = \mu$ and $Var(X_i) = \sigma^2$.
$$\begin{aligned}
    \overline{X_n} &= \frac{1}{n} (X_1 + \cdots + X_n) \\
    Var(\overline{X_n})
    &=
        \frac{\sigma^2}{n}
\end{aligned}$$

Then
$$\begin{aligned}
    \frac{\overline{X_n} - \mu}{\sigma/\sqrt{n}}
\end{aligned}$$
> ***tip***
> For large $n$ (usuallly $n \ge 30$), $\overline {X_n} = \frac{1}{n} (X_1 + \cdots + X_n)$ is approximately normal.
> 
> For $n$ large,
> $$\begin{aligned}
>     \overline{X_n} \approx N\left(\mu, \frac{r^2}{n}\right)
> \end{aligned}$$

#### Example
We roll a fair die
$X =$ outcome of the roll
$X$ is a discrete uniform RV,
$$\begin{aligned}
    \mu &= E[X] = 3.5 \\
    Var(X) &= \frac{35}{12}
\end{aligned}$$

Let's roll the die 30 times.
$$\begin{aligned}
    \overline X = \frac{1}{30}(X_1 + \cdots + X_n)
\end{aligned}$$
By the central limit theorem,
$$\begin{aligned}
    \overline X &\approx N\left(35, \frac{\sigma^2}{30}\right)= N(3.5, 0.0975)
\end{aligned}$$
- if we actually perform the experiment, the variance is so small that the probability that the outcome is significantly different from $3.5$ is very small. 

> ***warning***
> How can we say if the sample size is large enough to make the central limit heorem applicable?
> - really dependent on the shape of the distribution.
> - Ex. if the distribution of $X$ is not symmetric or weird 

