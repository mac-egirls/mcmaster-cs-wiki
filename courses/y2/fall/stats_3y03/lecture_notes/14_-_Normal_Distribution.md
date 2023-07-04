---
title: 14 - Normal Distribution.md
description:
published: false
date: 2023-07-03 00:49:52.996971
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.996973
---

2022-10-06

# Normal Distribution
- the pdf of a normal distribution is the classic bell curve
- this distribution is super important

We write $X \textasciitilde N(\mu, \sigma^2)$ iff
$$\begin{aligned}
	f_X(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-(x-\mu)^2/2\sigma^2}
\end{aligned}$$

##### Trouble
$e^{-(x-u)^2}$ has no nice antiderivative

#### Question
if $X \textasciitilde N(\mu, \sigma^2)$, how do we find $P(X \le x)$?
- look up values in a table

> ***Standard normal distribution***
> We will say $Z$ has a standard normal distribution iff $z \textasciitilde N(0, 1)$ we define
> 
> $$\begin{aligned}
> 	\Phi(Z) = P(Z \le z)
> \end{aligned}$$
> - $P(Z \le z)$ - the cdf of the stndard normal

## Nice Property of Normal Distributions
Suppose $X \textasciitilde N(\mu, \sigma^2)$. Then,
$$\begin{aligned}
	\frac{X-\mu}{\sigma} \sim N(0, 1)
\end{aligned}$$

$$Var(aX) = a^2 Var(X)$$
$$\begin{aligned}
	a = \frac{1}{\sigma}, Var\left(\frac{X}{\sigma}\right) = \frac{1}{\sigma^2}Var(X) = \frac{\sigma^2}{\sigma^2} = 1
\end{aligned}$$

Suppose we have $X \sim N(\mu, \sigma^2)$
We want to know $P(X \le x)$

### Observation
$$X \le x \iff \frac{X - \mu}{\sigma} \le \frac{x - \mu}{\sigma}$$
So to get from $x \sim N(\mu, \sigma^2)$ to $x\sim N(0, 1)$, then we must do the following:
$$\begin{aligned}
	P(X \le x) 
	&=
    	P\left(\frac{X-\mu}{\sigma}\right)
    \\&=
        P\left(z \le \frac{x-\mu}{\sigma}\right)
    \\&=
        I\left(\frac{x-\mu}{\sigma}\right)
\end{aligned}$$

#### Example
File transfer speed from server to computer is normally distributed with mean 5.75 mbps and variance $0.35^2$

What is the probability speed $\ge 6.7$.

$$\begin{aligned}
	X &= \text{transfer speed} \\
	X &\sim N(5.75, 0.35^2)
\end{aligned}$$

*Want:*
$$\begin{aligned}
	 P(X \ge 6.7)
	 &=
    	1 - P(X < 6.7)
	 \\&=
    	1 - P(X \le 6.7)
    \\&=
        1 - P\left(Z \le \frac{6.7-5.75}{0.35}\right)
    \\&=
        1 - I(2.71)
    \\&=
        1 - 0.996636
    \\&=
        0.003364
\end{aligned}$$


*Suppose* we want the spread such that the probability that $\mu - s \le X \le u+s$ is $99\%$.

Want to find $s \ge 0$ s.t.

$$P(5.75 - s \le X \le 5.75+s) = 0.99$$

### Observation
$$\begin{aligned}
	1 = P(X < 5.75 - s) + P(5.75-s \le X \le 5.75+s) + P(X>5.75+s)
\end{aligned}$$

The pdf of $X$ is symmetric so
$$\begin{aligned}
	P(X < 5.75-s) = P(X>5.75+s)
\end{aligned}$$

So
$$\begin{aligned}
    0.99 &= P(5.75-s \le X \le 5.75+s) \\
	1 &= 0.99 + 2P(X<5.75-s) \\
	0.99 &= 1 - 2P(X<5.75-s) \\
	0.99 &= 1 - 2P\left(Z \le \frac{(5.57-s)-5.75}{0.35}\right) \\
	0.99 &= 1 - 2\Phi \left(\frac{-t}{0.35}\right) \\
	-\frac{0.99-1}{2} &= \Phi \left(\frac{-t}{0.35}\right) \\
	0.005 &\approx \Phi \left(\frac{-t}{0.35}\right) \\
	0.005 &\approx \Phi \left(-2.57\right) \\
	\frac{-t}{0.35} &\approx -2.57 \\
	t &= 2.57 \cdot 0.35 = 0.8995
\end{aligned}$$

$\therefore$ 99% of the probability is in the interval $(5.75-0.9, 5.75+0.9)$

