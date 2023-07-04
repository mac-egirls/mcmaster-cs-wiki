---
title: 4 - combinatorics.md
description:
published: false
date: 2023-07-03 00:49:52.994814
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.994816
---

We want to get from situation 1 to situation 2

| Situation 1 | Situation 2 |
|-|-|
|$(1, 4, 6)$|$\{1,4,6\}$|
|$(1, 4, 6)$|$\{1,4,6\}$|
|$(4, 1, 6)$|$\{1,4,6\}$|
|$(4, 1, 6)$|$\{1,4,6\}$|
|$(6, 1, 4)$|$\{1,4,6\}$|
|$(6, 1, 4)$|$\{1,4,6\}$|

$\{1, 4, 6\}$ identifies all arrangements in situation 1! So divide.


> ***Conclusion***
> The number of ways we can choose 3 things from a set of 5 is $\frac{6 \cdot 5 \cdot 4}{3!}$.
> 
> $$\begin{aligned}
> 	\frac{6 \cdot 5 \cdot 4}{3!}
> 	&= \frac{6 \cdot 5 \cdot 4 \cdot 3!}{3! \cdot 3!}
> 	\\&= \frac{6!}{3! \cdot 3!}
> 	\\&= \binom{6!}{3!}
> \end{aligned}$$


## General Situation
- $n$ objects
- Want to choose $0 \le r \le n$
- If order doesn't matter
$$\begin{aligned}
	&\frac{n(n-1)(n-2) \cdots (n-r+1)}{r!}
	\\&= 
 	\frac{n(n-1)(n-2) \cdots (n-r+1)(n-r) \cdots 1}{r!(n-r) \cdots 1}
	\\&= 
 	\frac{n!}{r!(n-r)}
 \\&= \binom{n}{r}
\end{aligned}$$


> ***Binomial Theorem***
>  $$(x+y)^n = \sum_{r=0}^{n-1} \binom n r x^n y^{n-r}$$
>  $$\binom n r = \binom{n}{n-r}$$

### Example: **An urn contains 5 red balls, 6 blue balls, 8 green balls. We reach in and choose 3**

#### Question: *How many ways can we draw in such a way that all the balls have the same colours?*

* There are $\binom 5 3$ many ways of choosing only red
* There are $\binom 6 3$ many ways of choosing only blue
* There are $\binom 8 3$ many ways of choosing only green

So in total, there are $\binom 5 3 + \binom 6 3 + \binom 8 3$ ways of choosing all one colour.

#### Question: *How many ways can we choose one of each colour?*
- red ball: $\binom 5 1$
- blue ball: $\binom 6 1$
- green ball: $\binom 8 1$

so in total, $\binom 5 1 \cdot \binom 6 1 \cdot \binom 8 1$.


## Axioms of Probability
If $S$ is our sample space, $\mathcal F$ is the set of events, then $P: \mathcal F \to [0, 1]$ is a probability $iff$
1) $P(S) = 1$
2) For mutually independent $E_1, E_2, \dots$
$$P(\bigcup_{i=1}^\infty E_i) = \sum_{i=1}^\infty P(E_i)$$


> ***Specific Situation: (Equally Likely Outcomes)***
> $S = \{s_i, \dots, s_n\}$
> Lets assume $P$ has the property that $P(\{s_i\}) = P(\{s_j\})$ for any $i, j$.
> $$\begin{aligned}
> 	1 &= P(\{s_1, \dots, s_n\})
> 	\\&= P(\bigcup_{i=1}^n \{s_i\})
> 	\\&= \sum_{i=1}^n P(\{s_i\})
> 	\\&= nP(\{s_i\})
> \end{aligned}$$
> $$P(\{s_i\}) = \dots = P(\{s_n\}) = \frac 1 n$$

### Example: **Roll a die 6 times**
Outcomes are 6 tuples $(r_1, r_2, \dots, r_6)$

How big is the sample space?
- $|S| = 6^6$ <- Why?
	- Because each roll has 6 different possibilities

### Example: **What is the probability that a 6 comes up at least once?**
$$\begin{aligned}
	&P(\text{one 6 or two 6 or ... six 6})
	\\&= P(one 6) + P(two 6) + \cdots + P(six 6)
\end{aligned}$$
Very tedious tho.

$A$ = at least one 6 comes up
$A'$ = no 6 comes up

What is $P(A')$?
$$P(A') = \frac{5^6}{6^6}$$
$$\begin{aligned}
	1 &= P(S) 
	\\&= P(A \cup A')
	\\&= P(A) + P(A')
	\\ \text{So } P(A) &= 1 - P(A')
\end{aligned}$$
And bam done.


