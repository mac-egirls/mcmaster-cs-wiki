---
title: 5 - conditional probability.md
description:
published: false
date: 2023-07-02 19:22:47.757077
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.757079
---

> *** Drawing an Ace with Friend***
> Probability of drawing an ace from a deck of playing cards -> $\frac{4}{52}$. If your friend draws before you what is the probability of you drawing an ace?
>
> There are 2 scenarios:
> 1. your friend drew an ace -> $\frac{3}{52}$
> 2. your friend didn't draw an ace -> $\frac{4}{51}$
> 
> The probability is conditional on another event that happened before

# Conditional Probability
Suppose we have two events $A, B \subseteq S$. We write $P(A | B)$ "probability of $A$ given $B$" to mean the probability of $A$ occurring given that we know $B$ has occurred.

What proportion of the probability in $B$ is coming from $A$?
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

### Question: **What is the probability that the sum of two rolls is greater than 7 given that the first roll is a 3?**

$$\begin{aligned}
	A &= \text{"The sum of the two rolls is > 7"} \\
	B &= \text{"The first roll is a 3"}
\end{aligned}$$

$$\begin{aligned}
	P(B) &= \frac{1 \cdot 6}{6 \cdot 6} = \frac 1 6 \\
	P(A \cap B) &= \ ?
\end{aligned}$$

What to know how many rolls satisfy $3 + n > 7$
- 3 - first roll
- $n$ - second roll

The only solution is $n = 5, 6$, so

$$\begin{aligned}
	P(A \cap B) &= \frac 2 {36} \\
	P(A|B) &= \frac{\frac 2 {36}}{\frac 1 6} \\
	&= \frac 1 3
\end{aligned}$$


> ***Product Rules***
> 1. $P(A \cap B) = P(B|A)P(A)$
> 2. $P(B \cap A) = P(A|B)P(B)$

### Example: Deck of Cards (Again yyaaayy)
$$\begin{aligned}
	A &= \text{"the first card is an ace"} \\
	B &= \text{"the second card is an ace"} \\
	P(A \cap B) &= P(A|B)P(B) = \frac 3 {51} \cdot \frac 4 {52}
\end{aligned}$$


> ***Theorem***
> Given a partition of the sample space, i.e., $E_1, \dots, E_n$ s.t.
> 1. $\bigcup_{i = 1}^n E_i = S$
> 2. for all $i \ne j, E_i \cap E_j = \emptyset$
> Then,
> $$\begin{aligned}
> 	P(B) &= P(B \cap E_1) + \cdots + P(B \cap E_n) \\
> 	&= P(B|E_1)P(E_1) + \cdots + P(B |E_n)P(E_n)
> \end{aligned}$$

