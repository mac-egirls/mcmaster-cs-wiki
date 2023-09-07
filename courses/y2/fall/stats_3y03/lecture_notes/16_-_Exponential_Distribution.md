---
title: 16 - Exponential Distribution.md
description: 
published: true
date: 2023-09-05T18:07:50.981Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:27:35.768Z
---

Consider an interval $T$. Suppose that some event occurs randomly according to some Poisson Distribution with rate $\lambda$.

Let $X =$ the length (from 0) until an event occurs.

$P(X > x) =$ Probability that no events occur in $[0, x]$. The distance to the first event exceeds $x$ ***iff*** there are no flaws within a length of $x$ millimetres.

Let $N_x$ = \# of events in $x$ millimeters of wire.
$$\begin{aligned}
    P(X > x) &= P(N_x = 0)
    \\&=
        \frac{e^{-\lambda x} (\lambda x)^0}{0!} = e^{-\lambda x}
\end{aligned}$$
So,
$$F(x) = P(X \le x) = 1 - e^{-\lambda x}$$

> ***exponential distribution***
> The random varialbe $X$ that equals the distance between successive events from a poisson process with mean number of events $\lambda > 0$ per unit interval is an *exponential random variable* with parameter $\lambda$.
> $$\begin{aligned}
>     f_X(x) = \lambda e^{-\lambda x}
> \end{aligned}$$
> We say $X$ is exponential with rate $\lambda$, $x \ge 0$

> ***expected value, variance***
> $$\begin{aligned}
>     E[X] &= \frac{1}{\lambda} \\
>     Var(X)&= \frac{1}{\lambda^2}
> \end{aligned}$$

#### Example
Average time between buses is 15 mins. Let's assume the time is exponential distributed. $\lambda = \frac{1}{15}$ (1 bus every 15 minutes)

*Q:* Get to the stop. What is the prob that the bus arrives in the next 5 mins? $X =$ length of wait.

$$\begin{aligned}
    P(X \le 5)
    &=
        1 - e^{-\lambda (5)}
    \\&=
        1 - e^\frac{-1}{3}
    \\&\approx
        28.3\%
\end{aligned}$$

*Follow-up:* suppose we have already waited 20 mins. What is the probability that the bus arrives in the next 5 mins given that we've waited 20 mins already?

$$\begin{aligned}
    P(X \le 25 | X \ge 20)
    &=
        \frac{P(20 \le X \le 25)}{P(X \ge 20)}
    \\&=
        \frac{F_X(25) - F_X(20)}{1 - F_X(20)}
    \\&=
        \frac{(1 - e^{\frac{-25}{15}} - (1 - e^\frac{-20}{15}))}{1 - (1-e^{\frac{-20}{15}})}
    \\&=
        1 - \frac{e^{\frac{-25}{15}}}{e^{\frac{-25}{15}}}
    \\&=
        1 - e^{\frac{-1}{3}}
\end{aligned}$$
***The same as our answer in the first question!***

> ***memoryless***
> Generally, $X$ is memoriyless iff
> $$\begin{aligned}
>     P(X \le t_1 + t_2 | X \ge t) = P(X \le t_2)
> \end{aligned}$$
> 
> Exponential RV's have this property.






