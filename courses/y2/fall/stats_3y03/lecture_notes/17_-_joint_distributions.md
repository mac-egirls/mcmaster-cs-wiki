---
title: 17 - joint distributions.md
description:
published: false
date: 2023-07-02 19:22:47.757841
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.757847
---

Let $X, Y$ be two CRV's which may or may not be related.

> ***note***
> A/the joint probability distribution function of $X$ and $Y$ is a function $f_{X, Y}(x, y)$ such that
> 
> 1. $f_{X,Y}(x, y) \ge 0$ for all $x, y$
> 2. $\int \int_{\mathbb{R}^2} f_{X, Y} (x, y)\ dx\ dy = 1$
> 3. for any region $R \subseteq \mathbb{R}^2$\
> $$P((X, Y) \in R) = \int \int_R f_{X,Y}(x, y)\ dx\ dy$$

#### Example
Suppose $X$ and $Y$ are CRV's with $0\le Y \le X \le 4$ and
$$\begin{aligned}
    f_{X,Y}(x, y) = \begin{cases*}
        C(x + y), 0\le y\le x\le 4 \\
        0, \text{otherwise}
    \end{cases*}
\end{aligned}$$

Let's find $c$ so that $f_{X,Y}$ is a jpdf. want
$$\begin{aligned}
    1 
    &= 
        \int\int_{\mathbb{R}^2} f_{X,Y}(x, y)\ dx\ dy
    \\&=
        \int_0^4 \int_0^x c(x+y)\ dy\ dx
    \\&=
        c \int_0^4 xy + \frac{y^2}{2}\Big|_0^x dy\ dx
    \\&=
        c \int_0^4 x^2 + \frac{x^2}{2} dy\ dx
    \\&=
        c \int_0^4 \frac{3}{2}x^2 dy\ dx
    \\&=
        c \int_0^4 \frac{3}{2}x^2 dy\ dx
\end{aligned}$$

So
$$\begin{aligned}
    f_{X, y}(x, y) = \begin{cases*}
        \frac{x+y}{32}, 0<y<x<4 \\
        0, \text{otherwise}
    \end{cases*}
\end{aligned}$$

is a joint pair of RV's.

Last time, $c = \frac 1 {32}$. Consider the region $R = \{(x, y): x<2, y<3\}$.
By the definition of the joint pdf:
$$\begin{aligned}
    P((x, y) \in R)
    &=
        \int \int_R \frac{x+y}{32}\ dx\ dy
    \\&=
        \int_0^2 \int_0^x \frac{x + y}{32}\ dy\ dx
    \\&=
        \frac{1}{8}
\end{aligned}$$

> ***uniform distribution in two dimensions***
> Suppose $R$ is some region in the plane which is bounded. 
> then the uniform distribution on $R$ is
> $$\begin{aligned}
>     f_{X,Y}(x, y) = \begin{cases*}
>         \frac{1}{Area(R)}, (x, y) \in R \\
>         0, otherwise
>     \end{cases*}
> \end{aligned}$$

# marginal  probabilities

> ***notation***
> Let $R \subseteq \mathbb{R}^2$ is a region.
> Let $a, b \in \mathbb{R}$.
> $$\begin{aligned}
>     R_X(a) &= \{y \in \mathbb{R}: (a, y) \in R\} \\
>     R_Y(b) &= \{x \in \mathbb{R}: (x, b) \in R\}
> \end{aligned}$$
> 
> The ***marginal probability distribution*** is the individual probability distributions of $X$ and $Y$.

#### Example
Marginal probabilities are, for any $a, b \in \mathbb{R}$
$$\begin{aligned}
    f_X(a) &= \int_{R_X(a)} f_{X, Y} (a, y)\ dy \\
    f_Y(b) &= \int_{R_Y(b)} f_{X, Y}(x, b)\ dx
\end{aligned}$$
Using these, we can recover the $E[X], E[Y], Var(X), Var(Y)$ as usual.

> ***note***
> $$\begin{aligned}
>     \int_{-\infty}^\infty f_X(x)\ dx &= \int_{-\infty}^\infty \int_{R_X(x)} f_{X, Y}(x, y)\ dy\ dx
>     \\&= 1
> \end{aligned}$$

Similarly, the other one.

#### Uniform Example
From earlier: consider the uniform distr. on $[0, 2]^2$.
$$\begin{aligned}
    f_{X,Y}(x, y) &= \frac{1}{4} \text{ on } R = [0, 2]^2
\end{aligned}$$
let's try to compute $f_X(x)$.

so

![](/images/20230702002435.png)
$$\begin{aligned}
    f_X(x)
    &=
        \int_{R_X(x)} f_{XY}(x, y)\ dy
    \\&=
        \int_{0}^2 \frac{1}{4}\ dy
    \\&=
        \frac{1}{4}(2-0) = \frac{1}{2}
\end{aligned}$$
$$\begin{aligned}
    f_X(x) = \begin{cases*}
        \frac{1}{2}, x \in [0,2] \\
        0, otherwise
    \end{cases*}
\end{aligned}$$

#### Exercise
Consider the uniform distribution on the unit circle
$$\begin{aligned}
    R &= \{(x, y): x^2 + y^2 \le 1 \}
    \\ So \\
    f_{X,Y}(x,y) 
    &= \begin{cases*}
        \frac{1}{\pi}, (x, y) \in R \\
        0, otherwise
    \end{cases*}
\end{aligned}$$
Try to compute the marginals.
What the marginal for the $X$ component?

$$\begin{aligned}
    f_X(x) &= \begin{cases*}
        \displaystyle \int_{-\sqrt{1-x^2}}^{\sqrt{1-x^2}} \frac{1}{\pi}\ dx, (x, y) \in R \\
        0, otherwise
    \end{cases*}
\end{aligned}$$

> ***Expected value***
> $$\begin{aligned}
>     E[X] &= \int_{-\infty}^\infty x f_X(x)\ dx
>     =
>         \int_{-\infty}^\infty \int_{-\infty}^\infty x f_X(x, y)\ dx\ dy
> \end{aligned}$$
