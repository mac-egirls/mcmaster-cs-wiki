---
title: 11 - relations and functions.md
description: 
published: true
date: 2023-08-19T23:27:39.872Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:11:10.934Z
---

# Tuples
> ***Ordered Pair***
> $$\begin{aligned}
>     (b, c) &= \{\{b\}, \{b, c\}\} \\
>     (c, b) &= \{\{c\}, \{b,c\}\} \ne \{\{b\}, \{b,c\}\} = (b,c) \\
>     (a, a) &= \{\{a\}\}
> \end{aligned}$$

# Cartesian Product
> ***Axioms***
> ***Axiom, Pair Equality***
> $$\begin{aligned}
>     (b, c) &= (b', c') \equiv b = b' \land c = c'
> \end{aligned}$$
> 
> ***Axiom, Cartesian Product***
> $$\begin{aligned}
>     S \times T &= \{b, c \mid b \in S \land c \in T: (b, c)\} \\
>     S \times T &= \{(b, c) \mid b \in S \land c \in T\} \\
> \end{aligned}$$
> ![](/images/20221121095851.png)

![](/images/20221121095912.png)
![](/images/20221121100404.png)
- Can extend all of these theorems to $n$ sets.

- ***relation*** on a cartesian product is simply a subset of the cartesian product. So they are a set of $n$-tuples
- A ***binary relationship*** like $B \times B$ is a (***binary***) relation on $B$.
- The ***empty relation*** on $B \times C$ is $\emptyset$
- The ***identity relation*** $i_B$ on $B$ is $\{x \mid x \in B: \langle x, x \rangle\}$

# Notations, Domain and Range of Relations
![](/images/20221121102254.png)

> ***Notation, Domain and Range, and Inverse***
> ***Domain and Range***
> $$\begin{aligned}
>     Dom(R) &= \{b : B \mid (\exists c \mid : b R c)\} = \{b \mid \exists c \in C: (b, c) \in R\} \\
>     Ran(R) &= \{c : C \mid (\exists b \mid : b R c)\} = \{c \mid \exists b \in B: (b, c) \in R\}
> \end{aligned}$$
> 
> - $B$ and $Dom.R$ do not have to be the same.
> 
> ***Notation***
> $$\begin{aligned}
>     \sim R \equiv (B \times C) \setminus R
> \end{aligned}$$
> 
> ***Inverse***
> $$\begin{aligned}
>     (b, c) \in R^{-1} \equiv (c, b) \in r
> \end{aligned}$$

> ***Properties of Inverse***
> 1. $Dom(R^{-1}) = Ran(R), Ran(R^{-1}) = Dom(R)$
> 2. $R \subseteq B \times C \Rightarrow R^{-1} \subseteq C \times B$
> 3. $(R^{-1})^{-1} = R$
> 4. $R \subseteq Q \equiv Q^{-1} \subseteq R^{-1}$

# Operations on Relations
> ***Composition/product***
> Let $R$ be a relation on $B \times C$ and $Q$ be a relation on $C \times D$.
> Then $R \circ Q$ is
> $$\begin{aligned}
>     (b, d) \in R \circ Q &\equiv (\exists c \mid c \in C: (b, c) \in R \land (c, d) \in Q)
>     b(R \circ Q)d \equiv (\exists c \mid : bRcQd)
> \end{aligned}$$
![](/images/20221121131504.png)

# Power of Relations
![](/images/20221121132020.png)

# Functions as Relations
![](/images/20221121132140.png)
- ***total*** - domain is defined everywhere in its universe.

> ***Notation***
> - $f: B \to C$ if $f$ is total
> - $f: B \rightsquigarrow C$ or $f: B \rightharpoonup C$, or $f: B \hookrightarrow C$ or $f: B \not \rightarrow C$
> - For each $f : B \rightsquigarrow C$, $f: Dom(B) \rightarrow C$ is total.

![](/images/20221121133027.png)
