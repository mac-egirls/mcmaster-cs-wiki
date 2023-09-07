---
title: 10 - Geometric Distribution.md
description: 
published: true
date: 2023-09-05T18:01:12.893Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:01:08.791Z
---

Suppose we have a Bernoulli trial with prob. $p$ of success.
- $X =$ # of independent trials until a successful trial
- $range(X) = \{1, 2, 3, \dots \}$

$$\begin{aligned}
	f_X(1) &= P(X = 1) = p \\
	f_X(2) &= P(X = 2) = (1-p)p \\
	f_X(3) &= P(X = 3) = (1-p)^2p \\
	&\ \ \vdots \\
	f_X(k) &= P(X = k) = (1-p)^{k-1} p
\end{aligned}$$

> ***Geometric Distribution***
> Suppose we have a GRV $X$ of a Bernoulli trial with probability $p$ of success. Then the probability of getting the first success on the $k^{th}$ trial is:
> $$f_X(k) = P(X = k) = (1-p)^{k-1} p$$
> - If $0 < p < 1$, then $0 < 1-p < 1$, so as $k \to \infty, P(x = k) \to 0$
> - $E[X] = \frac 1 p$
> - $Var(X) = \frac{1-p}{p^2}$

#### Example
- Suppose we have a Bernoulli trial with prob $p$ of success.
- Choose an integer $r \ge 1$.
- We can ask: how many independent trials need to occur to see $r$-many successes?
- What is the range of $X =$ # of trials until $r$ success
- Let $n \in range(X)$.
- There are $\binom{n-1}{r-1}$ many ways to assign $r-1$ success and failures. (the $r^{th}$ success is the last trial, so we only permute $n-1$ trials as well.)

$$\begin{aligned}
	P(X = n) &= \binom{n-1}{r-1}(1-p)^{n-r}p^{r-1}p
	\\&= \binom{n-1}{r-1}(1-p)^{n-r} p^r
\end{aligned}$$

So when $r = 1$, we get back the pmf of a geometric RV.

> ***Negative Binomial Distribution***
> In a series of Bernoulli Trials, let $X$ be the RV, which is the number of trials until $r$ successes. Then $X$ is a *negative binomial random variable*, with parameters $0<p<1$, and $r = 1,2,3, \dots, n$, and
> 
> $$\begin{aligned}
> 	P(X = n) = \binom{n-1}{r-1}(1-p)^{n-r} p^r
> \end{aligned}$$


> ***Expected Value and Variance***
> $$\begin{aligned}
> 	E[X] &= \frac r p \\
> 	Var(X) &= \frac{r(1-p)}{p^2}
> \end{aligned}$$


#### Example: Negative Binomial Sampling
Suppose, you, a red-head, want to form a group of red-reads. You don't know any red heads, so you start calling random people and asking their hair colour.

*Q:* Suppose no more than $2\%$ of people have red hair. What is the probability that you talk to 10 red heads if you make 50 calls? 500 calls? or 1000?

**Solution:**
A given call is a Bernoulli trial with $p = \frac 2 {100} = \frac 1 {50}$.
- Say $X=\#$ of calls we need to make until we talk to 10 red heads.
- so pmf
$$\begin{aligned}
	f_X(n) &= \binom{n-1}{10-1}\left(1-\frac 1 {50}\right)^{n-10}\left(\frac 1 {50}\right)^{10} \\
	f_X(50) &= 9.376 \cdot 10^{-9} \approx 0 \\
	f_X(500) &\approx 0.0025 \\
	f_X(1000) &\approx 0.00005
\end{aligned}$$

So as $n \to \infty, f_X(n) \to 0$

In a random sample of 1000 people, we expect to talk to $20$ red heads.


