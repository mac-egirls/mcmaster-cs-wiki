---
title: 2 - boolean expressions.md
description: 
published: true
date: 2023-09-05T18:06:46.467Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:11:28.877Z
---

# Boolean Expressions

> ***Truth Values***
> - ***Values***: $false$ and $true$
> - ***Type***: $\mathbb B$
> - ***Boolean operators***:
>   - $\neg\_ : \mathbb B \to \mathbb B$ - negation
>   - $\_\lor\_ : \mathbb B \times \mathbb B \to \mathbb B$ - conjunction
>   - $\_\land\_ : \mathbb B \times \mathbb B \to \mathbb B$ - disjunction
>   - $\_\Rightarrow \_ : \mathbb B \times \mathbb B \to \mathbb B$ - implication
>   - $\_\Leftarrow \_ : \mathbb B \times \mathbb B \to \mathbb B$ - consequence
>   - $\_\Leftrightarrow \_ : \mathbb B \times \mathbb B \to \mathbb B$ - equivalence
>   - $\_\not\Leftrightarrow\_ : \mathbb B \times \mathbb B \to \mathbb B$ - inequivalence

## Definition
The *dual* $P_D$ of a boolean expression $P$ is constructed from $P$ by interchanging occurrences of
1. $true$ and $false$,
2. $\land$ and $\lor$,
3. $\equiv$ and $\not \equiv$
4. $\Rightarrow$ and $\not \Leftarrow$ and
5. $\Leftarrow$ and $\not \Rightarrow$

![](/images/20220919184518.png)
They are not quite the same as negation.

> ***Metatheorem Duality***
> 1) $P$ is valid $iff$ $\lnot P_D$ is valid
> 2) $P \equiv Q$ is valid $iff$ $P_D \equiv Q_D$ is valid.

## Definition
Let $P$ be a boolean expression. $P$ is...
- *satisfied* if it is $true$ in that state.
- *satisfiable* if there is a state in which it is satisfied
- *valid* if it is satisfied in every state.

- A valid boolean expression is called a *tautology*

## Modeling English Propositions
![](/images/20220908131522.png)


