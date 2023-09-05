---
title: 10 - induction and loops.md
description: 
published: true
date: 2023-08-19T23:27:36.377Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:11:07.298Z
---

> ***Axiom: Mathematical Induction over $\mathbb N$***
> $$\begin{aligned}
>     \forall (n: \mathbb{N} \mid : \forall (i \mid 0 \le i < n: P(i)) \Rightarrow P(n)) \Rightarrow \forall (n : \mathbb{N} \mid : P(n))
> \end{aligned}$$

> ***Theorem: Mathematical Induction over $\mathbb N$***
> $$\begin{gather*}
>     \forall (n: \mathbb{N} \mid : \forall (i \mid 0 \le i < n: P(i)) \Rightarrow P(n)) \iff \forall (n : \mathbb{N} \mid : P(n))
>     \\
>     P(0) \land \forall (n: \mathbb{N} \mid : \forall (i \mid 0 \le i < n: P(i)) \Rightarrow P(n+1)) \Rightarrow \forall (n : \mathbb{N} \mid : P(n))
> \end{gather*}$$

![](/images/20221120152838.png)
![](/images/20221120153213.png)

More generally,
![](/images/20221120160300.png)
![](/images/20221120160520.png)
![](/images/20221120160612.png)

![](/images/20221120160816.png)

![](/images/20221120160846.png)

![](/images/20221120174515.png)

![](/images/20221120174533.png)

![](/images/20221120180418.png)
- $\lnot B$ is an exit condition since it has to be $\lnot B$ to exit out of the loop

> ***Steps to prove***
> 1. Prove $P$ is *true* with the base case of *induction*.
> ![](/images/20221120190909.png)
> 2. we prove first that $\{P \land B \}\ i, p := i + 1, p+x\ \{P\}$ holds. $P[i, p := i+1, p+x] \Rightarrow B \land P$.
> 3. We prove that $P$ is true upon termination with the *inductive step*
> 4. $P \land i = n$ holds upon termination: $P \land \lnot B \Rightarrow P \land i = n$.

#### Example
![](/images/20221120202548.png)

![](/images/20221120203532.png)

- Do reverse to do thing

![](/images/20221121001301.png)

#### Example
![](/images/20221121001248.png)







