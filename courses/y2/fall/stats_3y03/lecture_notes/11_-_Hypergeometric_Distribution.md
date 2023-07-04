---
title: 11 - Hypergeometric Distribution.md
description:
published: false
date: 2023-07-03 00:49:52.991973
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.991975
---

#### Example
- Shuffled deck of cards
	- 4 aces, 48 other cards
	- Suppose we draw a sample of 4 cards (without replacement)
	- Let $X =$ # of aces in the draw ($range(X) = \{0, \dots, 4\}$)
- What is the pmf?
$$\begin{aligned}
	P(X = 0) &= \frac{48}{52} \cdot \frac{47}{51} \cdot \frac{46}{50} \cdot \frac{45}{49} \\
	P(X = 1) &= \frac 4 {52} \cdot \frac{48}{51} \cdot \frac{47}{50} \cdot \frac {46}{49} \cdot 4 \\
	P(X = 3) &= \frac{\binom 4 3 \binom{48} 1}{\binom{52}{48}}
\end{aligned}$$

This is an example of a hyper geometric RV.
> ***Hyper Geometric Distribution***
> Given a set of $N$ objects with $k$-many we consider successful (so $N-k$ failures) and our experiment consists of chosen $n$ objects (out of $n$) without replacement $(n \le N, k \le N)$, Let
> $$X = \text{\# of successes in $n$ draws}$$
> Then $X$ is a hyper geometric RV, and
> $$P(X = x) = \frac{\binom k x \binom{N-k}{n-x}}{\binom N n}$$
> 
> - $range(X) = max\{0, n+k - N\}$ to $min\{k, n\}$

> ***Expected Value and Variance***
> If $X$ is hyper geometric RV, then
> $$\begin{aligned}
> 	E[X] = np && Var(X) = np(1-p)\left(\frac{N-n}{N-1}\right)
> \end{aligned}$$
> Where $p = \frac k N =$ the probability of success the first draw
> 
> #### Remark
> If $n << N$, then $\frac{N-n}{N-1} \textasciitilde 1$ and so $X$ is approximately $Binomial(n, \frac k N)$.

