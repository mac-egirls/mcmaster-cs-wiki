---
title: 7a - model theory.md
description: 
published: true
date: 2023-09-05T18:00:51.779Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:00:48.588Z
---

![](/images/20221031141915.png)

- *Formula* - a well formed expression over the alphabet defined above.
- $R_i(x_1, \dots, x_n)$ - atomic formula
    - $n$ - the arity of $R_i$
    - All occurrences of $R_i$ must have the same arity

> ***Def. of Formula***
> $\phi$ is a ***formula*** iff:
> 1. $\phi$ is atomic
> 2. $\phi = \phi_1 \land \phi_2, \phi = \phi_1 \lor \phi_2, \phi = \lnot \phi$, where $\phi_1$, $\phi_2$ are formulas.
> 3. $\phi = \exists\phi, \phi = \forall \phi$

- ***Prenex Normal Form:*** all quantifiers appear in the front of the formula.
- ***Free Variable:*** not bound by any quantifier
- ***Sentence***, ***statement:*** no free variables

#### Examples
![](/images/20221031143835.png)

> ***model***
> a ***model*** (Interpretation, structure) is a tuple
> $$\begin{aligned}
>     M = (U, P_1, \dots, P_k)
> \end{aligned}$$
> where 
> - $U$ is the *universe* over which variables may take values.
> - $P_i$ is a *relation* assigned to the symbol $R_i$
> - A *language of a model* is the set of all formulas of the model
> - If the formula $\phi$ is *true* in a model $M$, we say that $M$ is a *model of* $\phi$.

#### Example
![](/images/20221031145538.png)


