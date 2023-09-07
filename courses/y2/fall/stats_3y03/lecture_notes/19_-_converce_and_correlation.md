---
title: 19 - converce and correlation.md
description: 
published: true
date: 2023-09-05T18:08:07.349Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:27:49.869Z
---

> ***converse and correlation***
> $f_{XY}(x, y)$ joint pdf for $X$ and $Y$.
> The ***covariance*** is a measure of the relationship between two random variables. To define covariance, we must find the expected value of a given function $h(X, Y)$:
> $$\begin{aligned}
>     E[h(X, Y)] &= \int \int_{\mathbb{R}^2} h(x, y) f_{XY} (x, y)\ dx\ dy
> \end{aligned}$$
> Intuitively, $E[h(X, Y)]$ is the weighted average of $h(x, y)$ for each point in the range of $(X, Y)$.
> 
> ***Special case:***
> $$h(x, y) = a_1x + a_2y$$
> 
> Then
> $$\begin{aligned}
>     E[a_1X + a_2Y]
>     &=
>         \int\int_{\mathbb{R}^2}(a_1X+a_2Y)f_{XY}(x, y)\ dx\ dy
>     \\&=
>         a_1 \int\int_{\mathbb{R}^2}X f_{XY}(x, y)\ dx\ dy + 
>         a_2 \int\int_{\mathbb{R}^2}Y f_{XY}(x, y)\ dx\ dy
>     \\&=
>         a_1 E[X] + a_2 E[Y]
> \end{aligned}$$
> 
> $$\begin{aligned}
>     Var(X)
>     &=
>         \int\int_{\mathbb{R}^2} x^2 f_{XY}(x, y)\ dx\ dy
>         - \left(\int\int_{\mathbb{R}^2} x f_{XY}(x, y)\ dx\ dy\right)^2
> \end{aligned}$$

> ***covariance***
> It's a way to detect linear relationships between two RV's.
> $$\begin{aligned}
>     \sigma_{XY} 
>     &=
>         E[XY] - E[X]E[Y]
>     \\&=
>         \int\int_{\mathbb{R}^2} xy f_{XY}(x, y)\ dx\ dy
>         - \int\int_{\mathbb{R}^2} x f_{XY}(x, y)\ dx\ dy
>         \int\int_{\mathbb{R}^2} y f_{XY}(x, y)\ dx\ dy
> \end{aligned}$$

Suppose $X$ and $Y$ are independent, Then
$$\begin{aligned}
    \int\int_{\mathbb{R}^2} xy f_{XY}(x, y)\ dx\ dy
    &=
        \int_{-\infty}^\infty \int_{-\infty}^\infty xy f_{X}(x) f_Y(y) \ dx\ dy
    \\&=
        \left(\int_{-\infty}^\infty x f_{X}(x) \ dx\right)
        \left(\int_{-\infty}^\infty y f_{Y}(y) \ dy\right)
    \\&=
        E[X]E[Y]
\end{aligned}$$
So if $X$ and $Y$ are independent, then $\sigma_{XY} = 0$.

> ***warning***
> $\sigma_{XY} = 0 \not \Rightarrow$ that $X$ and $Y$ are unrelated (they could have non-linear relationship).

#### Exercise
Let $X \sim Unif([-1, 1])$. Let $Y = X^2$.
Check: $\sigma_{XY} = 0$. But $X$ and $Y$ are *not* independent.

> ***correlation***
> Is a measure of linear relationship (like covariance) but is easier to understand.
> $$\begin{aligned}
>     f_{XY} &= \frac{\sigma_{XY}}{\sigma_X\sigma_Y}
> \end{aligned}$$
> 
> ***Excercise:***
> $$\begin{aligned}
>     -1 \le f_{XY} \le 1
> \end{aligned}$$
> 
> ***Fact:***
> if $f_{XY} = \pm 1$, then $Y = aX+b$ where $f_{XY}$ is the sign of the slope.

Suppose $h(X_1, \dots, X_n) = \sum_{i=1}^n a_i X_i$.
*Fact:* $E\left[c + \sum_{i=1}^n a_i X_i\right] = c + \sum_{i=1}^n a_i E[X_i]$ 

Weirder:
$$\begin{aligned}
    V\left(c + \sum_{i=1}^n a_i X_i\right)
    &=
        \sum_{i=1}^n a_i^2 V(X_i) +
        2 \sum_{i < j} a_i a_j \sigma_{X_i X_J}
\end{aligned}$$

***Special case***
If $X_1, \dots, X_n$ are indep., then
$$\begin{aligned}
    V\left(c + \sum_{i=1}^n a_i X_i\right)
    &=
        \sum_{i=1}^n a_i^2 V(X_i)
\end{aligned}$$

***Super Special Case***
Let $X_1, \dots, X_n$ are indep. RV's.
Let $\overline X = \frac{1}{n}(X_1 + \cdots + X_n)$ (the average)

Assume $E[X_i] = \mu_i$, $V(X_i) = \sigma_i^2$. Then
$$\begin{aligned}
    E[\overline X] &= \frac{1}{n}(\mu_1 + \cdots \mu_n) \\
    V(\overline X) &= \frac{1}{n^2} \sum_{i=1}^n \sigma_i^2
\end{aligned}$$
If $\mu_i = \mu$ and $\sigma^2_i = \sigma^2 \forall i,$ then
$$E[\overline X] = \frac{n\mu}{n}=\mu, V(\overline X) = \frac{n\sigma^2}{n^2}=\frac{\sigma^2}{n}$$
