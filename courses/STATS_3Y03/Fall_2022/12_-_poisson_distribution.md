---
title: 12 - poisson distribution.md
description: 
published: true
date: 2023-09-05T18:01:22.293Z
tags: stats, 3y03
editor: markdown
dateCreated: 2023-09-05T18:01:19.077Z
---

- The poisson distribution decides events which occur randomly in an interval at a fixed rate.

#### Example
- \# of flaws in a length of wire
- \# of earthquakes in a 5 year period
- \# of busses at a stop in a given week

What do we need for the pmf?
- The average \# of events per unit interval ($\lambda$)

> ***Poisson Probability Mass Function***
> 
> $$\begin{aligned}
> 	f_X(x) &= \lim_{n \to \infty} \binom n x \left(\frac{\lambda T} n\right)^x \left(1 - \frac{\lambda T}n\right)^{n - x}
> 	\\&=
> 		\frac{(\lambda T)^x}{x!} e^{-\lambda T}
> \end{aligned}$$
> 
> $$\begin{aligned}
> 	E[X] &= \lim_{n \to \infty} np = \lim_{n \to \infty} \frac{n \lambda T}{n} = \lambda T \\
> 	Var(X) &= \lambda T
> \end{aligned}$$
> 

#### Example
A real estate agency sells on average 2 houses/day.

What is the probability that they sell 10 houses next week?
- $T =$ 7 days
- $\lambda =$ 2 houses/day
- $X =$ \# of houses sold per week

$$E[X] = \lambda T = 14 \text{ per week}$$
$$\begin{aligned}
	P(X = 10) &= ? \\
	f_X(10) &= \frac{e^{-14} 14^{10}}{10!}
	\\&= 0.066 \textasciitilde 6.6\%
\end{aligned}$$

> ***Observations***
> - $x!$ dombinates the value of $f_X(x)$
> - So $f_X(x)$ drops to 0 very quickly


