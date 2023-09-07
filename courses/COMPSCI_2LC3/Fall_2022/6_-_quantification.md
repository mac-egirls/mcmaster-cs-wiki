---
title: 6 - quantification.md
description: 
published: true
date: 2023-09-05T18:00:42.733Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:00:38.658Z
---

- Can express quantification by
    - summing a set of values
    - making disjunction of a set of boolean values

# Types
- *Expressions* must be *type correct* and satisfy the normal rules of syntax concerning balanced parenthesis.

#### Example
$$\begin{aligned}
	x : \mathbb{Z} && p: \mathbb{B} && y: \mathbb{R}
\end{aligned}$$
- Types can be mentioned in the expression to make it clear to the reader
$$\begin{aligned}
	1^n \equiv (1 : \mathbb{Z})^{n:\mathbb{N}}
\end{aligned}$$

- *type correctness*, the act of putting the right types as arguments to functions, depends only on the sequence of symbols in the proposed expression, and not on evaluation of the expression.

#### Example
$$\begin{aligned}
	\frac{1}{(x : \mathbb{Z})}: \mathbb{R}
\end{aligned}$$
is an expression, but evaluation is undefined when $x = 0$

> ***$E \in t$***
> If $E: t$, then $E \in t$ evaluates to true in all states in which $E$ is *well defined*
- In $E[x:=F]$, $x$ and $F$ must have the same type.
- $b=c$ is defined only when $b$ and $c$ have the same types.

- *subtypes* - $\mathbb{N} \subseteq \mathbb{Z}$, so $I: \mathbb{Z}$ and $I:\mathbb{N}$ are suitable declarations
- *overloading* - same operators can be used on different types
- *polymorphism* - $= : t \times t \to \mathbb{B}$ is polymorphic because it is defined for any type $t$.

# Syntax and Interpretation of Quantification
> ***Linear Notation***
> $$\begin{aligned}
> 	\sum_{i=1}^n e \equiv +(i|1 \le i \le n: e)
> \end{aligned}$$
> - $e$ - an expression
> - $1 \le i \le n$ - apply $e$ to any $i$ in the interval
![](/images/20221004135942.png)

> ***Abelian Monoid***
> Let $*$ be any operator satisfying
> - ***Symmetry/Commutativity***
> - ***Associativity***
> - ***Identity*** $u$: $u*b = b = b*u$
> 
> A set of values together with an operator $*$ that satisfy the above is called an *Abelian Monoid*

> ***Quantification over $*$***
> The general form of a quantification over $*$ is 
> $$\begin{aligned}
> 	*(x : t_1, y: t_2 | R: P)
> \end{aligned}$$
> - $x \ne y$
>     - Called *bound variables* or *dummies of the quantification*
> - $t_1$ and $t_2$ are the types of dummies $x$ and $y$
>     - if $t_1 = t_2$, then can write $*(x, y: t_1 | R : P)$
> - $R$ - boolean, the range of the quantification
>     - If $R$ is omitted, then the range is $true$
>     - may refer to $x, y$
> - $P$ - an exression, the *body of the quantification*
>     - may refer to $x, y$
> - The type of the result is the type of $P$
> 
> - It denotes the application of operator $*$ to the values $P$ for all $x: t_1, y: t_2$ for which range $R$ is true.

## Free and Bound Occurrences of Variables
![](/images/20221004232401.png)
- $i>0$ is *free*, and during evaluation is replaced by the value of $i$
- every other occurrence is *bound*
- The *free* occurrence of $i$ is a different variable to the *bound* occurrence
    - This is confusing, so occurrences should be renamed
- Can think of $i>0$ as an *outer scope* and the $\land i$ as an *inner scope* like in code.

![](/images/20221004141603.png)

> ***$occurs('v', 'e')$***
> At least one variable in the list $v$ of variables occurs free in at least one expression in expression list $e$.

![](/images/20221004141614.png)

#### Example
![](/images/20221004232120.png)
- leftmost occurrence of dummy $i$ is free
- leftmost occurrence of $j$ and exponent of $j$ in the first summation is free
- All other occurrences are bound to different scopes

![](/images/20221004233830.png)
> ***Theorem***
> Provided $\lnot occurs('y', 'x,F')$,
>     $$*(y|R:P)[x:=F] = *(y|R[x:=F]:P[x:=F])$$

#### Examples
$$\begin{aligned}
	+(x\mid1 \le x \le 2: y)[y := y+z]
    	&=  +(x\mid 1 \le x \le 2: y+z)\\
    +(y\mid 0\le y <n:b[y]=n)[n:=y] 
    	&= +(j\mid 0\le j <n:b[j]=y) \\
    +(y\mid 0\le y <n:b[y]=n)[y:=m] 
    	&= +(j\mid 0\le j <n:b[j]=n) \\
\end{aligned}$$

# Rules about Quantification
Similar to [Leibniz](/courses/y2/fall/compsci_2lc3/lecture_notes/6_-_quantification.md), 
![](/images/20221004235438.png)
- Top: applies quantification on both sides; substitution happens in the condition.
- Top: applies quantification on both sides; substitution happens in the returned expression.

## Axioms
![](/images/20221004235526.png)
- *One point* as in there's only one result to the quantification

![](/images/20221004235919.png)
![](/images/20221004235956.png)
- Can think of $R$ and $S$ being mutually exclusive, so they can't be true at the same time so splitting them up is valid

![](/images/20221005000100.png)
- $(*x \mid R\land S: P)$ accounts for the double counting when $R \land S$ is true
- The more general theorem of *(8.16)*

![](/images/20221005000149.png)
- Idempotency means $x * x = x$ so double counting means nothing

![](/images/20221005001104.png)
![](/images/20221023201517.png)

# manipulating ranges
![](/images/20221023201711.png)
![](/images/20221023201753.png)
![](/images/20221023201757.png)
