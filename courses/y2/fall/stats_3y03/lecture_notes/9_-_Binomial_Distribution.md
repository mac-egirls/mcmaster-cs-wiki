---
title: 9 - Binomial Distribution.md
description:
published: false
date: 2023-07-03 00:49:52.996815
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.996817
---

# Binomial Distribution
- Consider $n$ independent experiments (trials)
- each trial has two possible outcomes *(success/failure)*
- outcomes are *mutually exclusive*

Most basic situation:
$X$ is a DRV
$$\begin{aligned}
	&P(X = 1) = p &P(X = 0) = 1 - p
\end{aligned}$$

$X \textasciitilde Bernoulli(p)$

#### Example: Roll a die
$$\begin{aligned}
	S &= \{1, \dots, 6\} \\
	X(S) &= \begin{cases*}
		1, \text{if } s = 1, \\
		0, \text{if } s = 2, \dots, 6
	\end{cases*}
\end{aligned}$$

A binomial RV with $n$ trials and probability $p$ of success is intuitively a sum of $n$ independent Bernoulli trials with probability $p$ of success.

#### Example: roll a die again
- we roll a die, rolling a $1 = success$
- Let's repeat this $n = 10$ times.
- $X =$ # of 1's we get out of 10 rolls.
	- $range(X) = \{0, \dots, 10\}$
- What is the probability mass function?
$$\begin{aligned}
	P(X = 0) &= \left(\frac 5 6\right)^{10} \\
	P(X = 1) &= \binom{10} 1 \left(\frac 1 6\right) \left(\frac 5 6\right)^9 \\
	&\ \ \vdots \\
	P(X = k) &= \binom{10} k \left(\frac 1 6\right)^k \left(\frac 5 6\right)^{10-k} \\
\end{aligned}$$


> ***General Situation***
> Given $n$ independent Bernoulli trials, each with probability $p$ of success. If 
> $$X = \text{\# of successes (out of $n$)}$$
> then say $X \textasciitilde Binom(n, p)$ and
> $$f_X(j) = \binom{n}{j} p^j (1 - p)^{n-j}$$
> where $j = 0, \dots, n$
> - $\binom n x$ ways of getting $x$ successes from $n$ trials.
> - $p^x$ is probability of succeses, $n$ times.
> - $p^{n-1}$ is the probability of failures, $n-1$ times.

#### Simple Example
- Tossing a coin 100 times
- $X =$ # of heads, then $X \textasciitilde binom(100, \frac 1 2)$ so,
$$P(X = k) = \binom{100}{k}(\frac 1 2)^k(\frac 1 2)^{100 - k}$$

Without computing, what is $E[X] = 50 = 100\frac 1 2$

> ***Expected Value and Variance***
> If $X \textasciitilde Binom(n, p)$ then,
> $$\begin{aligned}
> 	E[X] &= np \\
> 	Var(X) &= np(1 - p)
> \end{aligned}$$

#### Example: test
- 27 multiple choice questions
	- 4 options
	- each question is independent
	- each question is $Bernoulli(\frac 1 4)$
- The test score is $X \textasciitilde Binom(27, \frac 1 4)$
- We What is the probability of passing if you guess every question?
- We need at least 14 to pass

$$\begin{aligned}
	P(X \ge 14) &= \sum_{j = 14}^{27} P(X = j) \\
	&= \sum_{j = 14}^{27} \binom{27}{j} (\frac 1 4)^j (\frac 3 4)^{27-j} \\
	&= 1 - \sum_{j = 0}^{13} \binom{27}{j} (\frac 1 4)^j (\frac 3 4)^{27-j}
	\\&= 0.00287
\end{aligned}$$

