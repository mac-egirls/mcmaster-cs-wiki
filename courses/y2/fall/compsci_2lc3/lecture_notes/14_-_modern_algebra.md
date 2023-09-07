---
title: 14 - modern algebra.md
description: 
published: true
date: 2023-09-05T18:06:38.361Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:11:19.717Z
---

2022-12-07

# The structure of algebras
- An algebra is a pair $(S, \Psi)$
    - $S$ is a ***carrier*** of the algebra
    - $\Psi$ is a list of operators
        - Each are a total function of type $S^m \to S$ for some $m$
        - $m$ is called the ***arity*** of the operator
        - Arity 0 operators are called ***nullary operators***; functions of no arguments
- The algebra is ***finite*** if its carrier $S$ is finite; otherwise, it is ***infinite***

# Signatures
- ***signature*** contains the name of the carrier and the operator types

> ***example***
> The altebra $(\mathbb{B}, \lor, \land, \lnot)$ has the signature
> $$\begin{aligned}
>     (\mathbb{B}, \mathbb{B}\times\mathbb{B} \to \mathbb{B}, \mathbb{B}\times\mathbb{B} \to \mathbb{B}, \mathbb{B} \to \mathbb{B})
> \end{aligned}$$

- Algebras have the same signature if
    1. same number of operators
    2. Corresponding operators have the same type structure. (Replacing every occurrence of first algebra's carrier with second algebra's carrier gets the type signature for the second algebra)

> ***example***
> The following 2 algebras have the same type signature:
> $$\begin{gather*}
>     (\mathbb{B}, \mathbb{B}\times\mathbb{B} \to \mathbb{B}, \mathbb{B} \to \mathbb{B}) \\
>     (\mathbb{C}, \mathbb{C}\times\mathbb{C} \to \mathbb{C}, \mathbb{C} \to \mathbb{C})
> \end{gather*}$$
> 
> The following 2 algebras *do not* have the same type signature:
> $$\begin{gather*}
>     (\mathbb{B}, \mathbb{B}\times\mathbb{B} \to \mathbb{B}, \mathbb{B} \to \mathbb{B}) \\
>     (\mathbb{C}, \mathbb{C} \to \mathbb{C}, \mathbb{C}\times\mathbb{C} \to \mathbb{C})
> \end{gather*}$$

# Special Values
## Identities
![](/images/20221207120207.png)

## Zeros
![](/images/20221207120234.png)

# Closures
 ![](/images/20221207121126.png)

# Subalgebras
![](/images/20221207121243.png)

# Isomorphism
![](/images/20221207121853.png)

![](/images/20221207122334.png)

# Automorphism
![](/images/20221207122637.png)

# Homomorphism
![](/images/20221207122718.png)
- An isomorphism is a homomorphism that is also one-to-one and onto.

![](/images/20221207123142.png)

# Lattices as Algebras
![](/images/20221207123346.png)

![](/images/20221207124635.png)

![](/images/20221207145633.png)

# Sequences
- ***Alphabet*** - an *arbitrary* (usually finite) set of elements, often denoted by the symbol $\sum$
- ***Sequence*** 
    - An element $x = (a_1, a_2, \dots, a_k) \in \sum^k$, where $\sum^k$ is a cartesian product of $\sum$'s.
        - For convenience, write $x = a_1 a_2 \dots a_k$
    - a function $\phi: \{1, \dots, k\} \to \sum$ such that $\phi(1) = a_1, \phi(2) = a_2, \dots, \phi(k) = a_k$
    - 2 interpretations above both represent the same thing
- If $\sum$ are all symbols, then a finite sequence of symbols is a ***string*** or ***word***.
- $|x|$ - ***length*** of a sequence $x$
- $\epsilon$ - sequence consisting of zero symbols, i.e., $|\epsilon| = 0$

# Concatenation
![](/images/20221207151932.png)

> ***Definition***
> $$\begin{aligned}
>     \textstyle\sum^* = \{a_1 \dots a_k \mid a_i \in \textstyle\sum \land k \ge 0\}
> \end{aligned}$$
> - the set of all sequences, including $\epsilon$, built from the elements of $\sum$

# Semigroups
![](/images/20221207152903.png)

> ***Definition***
> Let $(S, \circ)$ be a semigroup. Then, the algebra $(T, \circ)$ is a ***subsemigroup*** if
> - $T \subseteq S$
> - $T$ is closed under $\circ$

# Monoids
> ***Definition***
> - A monoid $(S, \circ, 1)$ is a semigroup $(S, \circ)$ with an identity 1.
> - If $\circ$ is also symmetric, the monoid is called ***Abelian***.
> - A subalgebra of a monoid that contains hte identity of the monoid is called a ***submonoid***.

![](/images/20221207154338.png)

#### Example
![](/images/20221207154345.png)

# Groups
![](/images/20221207154549.png)

## Theorems of Groups
![](/images/20221207154744.png)

![](/images/20221207154820.png)

# Boolean Algebra
![](/images/20221207155012.png)

## Theorems
![](/images/20221207155033.png)

![](/images/20221207155746.png)

![](/images/20221207155940.png)

# Atoms
![](/images/20221207160224.png)

![](/images/20221207160331.png)

Let $B$ be a non-empty set. Then
$$\begin{aligned}
    B &= \bigcup\{\{b \} \mid: b \in B\} \\
    &= \bigcup_{b \in B} \{b\}
\end{aligned}$$
![](/images/20221207160740.png)

![](/images/20221207160806.png)

![](/images/20221207160819.png)

![](/images/20221207160920.png)

![](/images/20221207160931.png)

$$\begin{aligned}
    \tan 2x
    &=
        8 \cos^2x - \cot x \\
    \frac{\sin 2x}{\cos{2x}}
    &=
        8 \cos^2 x - \frac{\sin x}{\cos{x}} \\
    \frac{\sin 2x}{\cos{2x}}
    &=
        8 \cos^2 x - \frac{\sin x}{\cos{x}}
\end{aligned}$$
