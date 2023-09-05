---
title: 5 - formal logic.md
description: 
published: true
date: 2023-08-19T23:28:02.405Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:11:40.115Z
---

# proof theory

A *formal logical system*, or *logic*, is a set of rules defined in terms of
- a set of *symbols*
- a set of *formulas* constructed from the symbols,
- a set of distinguished formulas called *axioms*, and
- a set of *inference rules*.

## inference rules

They allow for formulas to be derived from other formulas.

$$\frac{H_1,H_2,\dots,H_n}{C}$$

- $H_1, H_2, \dots, H_n$ are the *premises* (or *hypotheses*)
- $C$ is its *conclusion*

> ***logical consistency***
> A logic is *consistent* if at least one of its formulas is a theorem and at least one is not; otherwise, the logic is *inconsistent*.

# Models
> ***PQ-L***
> A logic that does not say what the formulas, axioms, and inferences mean. It forcefully illustrates that a logic is a system for manipulating symbols, independent of meaning.

# Example
![](/images/20220930181257.png)
#### addition-equality interpretation
A formula $a$ P $b$ Q $c$ is mapped to $\#a + \#b = \#c$, where $\#x$ denotes the number of dashes in sequence of $x$.

#### addition-inequality interpretation
A formula $a$ P $b$ Q $c$ is mapped to true iff $\#a + \#b = \#c$, where $\#x$ denotes the number of dashes in sequence of $x$.

These 2 interpretations of the same PQ-L logic are different.

- Formulas have meaning with respect to a domain by defining which formulas are *true* and *false* statements about the domain.

> ***satisfiable***
> Let $S$ be a set of interpretations for a logic and $F$ be a formula of the logic. $F$ is *satisfiable* (under $S$) iff at least one interpretation of $S$ maps $F$ to $true$. 
> 
> $F$ is ***valid*** (under $S$) iff every interpretation in $S$ maps $F$ to $true$.
 %% Screw this %%
    ![](/images/20220930180356.png)

- **Soundness** - the theorems are true statements about the domain
- **Completeness** - every valid formula can be proved

#### Example: Non PQ-L
![](/images/20220930181550.png)

#### Example: Valid PQ-L
![](/images/20220930181637.png)

#### Example: Proof with axioms
![](/images/20220930181658.png)

> ***hereditary base-$n$ notation***
> Every exponent is also written in base $n$. So
> $$\begin{aligned}
>     2^5 + 2^1 + 2^0
> \end{aligned}$$
> in hereditary base-$n$ notation is
> $$\begin{aligned}
> 	2^{2^2+1}+2+1
> \end{aligned}$$

> ***Goodenstein sequence***
> Let $m$ be a number, and its Goodenstein sequence $G(m)$. $G(m)$ is defined as as follows:
> - the first element is $m$.
> - The $i^{th}$ element is given by
>     - write the $(i-1)^{th}$ element in hereditary base $i+1$ notation
>     - change all $i+1$'s to $i+2$'s
>     - subtract 1 from the result
>     
> ### Goodstein's theorem
> 
> Every Goodstein sequence eventually terminates at 0, no matter what the starting value is.
![](/images/20220930183533.png)

![](/images/20220930184308.png)
- predicate logic is an extension of a propositional logic with variables

![](/images/20220930185108.png)

# Constructive Logics
Let $P$ be any mathematical statement whose truth is not known. Then, we have
$$x = \begin{cases*}
	0 \text{ if $P$ is $true$} \\
	1 \text{ if $P$ is $false$} \\
\end{cases*}$$
Then $x$ is defined unambiguously, but we don't know whether $P$ is true. This is a ***non-constructive*** definition of $x$. A ***constructive*** definition would tell how to calculate the value of $x$.

> ***Notation***
> $$\begin{aligned}
>     A_0, \dots, A_n \vdash Q && or && \vdash_L Q
> \end{aligned}$$
> Where $L$ is the name of the logic with axioms $A_0, \dots, A_n$.
> 
> - $A_i$ are *premises of the sequent*, $Q$. 
> - Read as "$Q$ is provable from $A_0, \dots, A_n$."
> 
> The difference between $\Rightarrow$ and $\vdash$ is that $Q$ must be a boolean expression in $\Rightarrow$ but with $\vdash$ it is not necessary.

![](/images/20220930190822.png)

> ***Not an inference rule***
> ![](/images/20220930191023.png)

