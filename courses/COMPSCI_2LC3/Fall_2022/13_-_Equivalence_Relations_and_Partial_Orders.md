---
title: 13 - Equivalence Relations and Partial Orders.md
description: 
published: true
date: 2023-09-05T18:00:08.942Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:00:05.579Z
---

> ***Definition***
> A relation $R$ is an ***equivalence relation*** *iff* it is reflexive, symmetric, and transitive. 
> 
> **AKA**
> $R \subseteq B \times B$ is an ***equivalence relation*** *iff*
> 
> $$\begin{aligned}
>     \forall b, c, d \in B, bRb \land (bRc \equiv cRb) \land (bRc \land cRd \Rightarrow bRd)
> \end{aligned}$$
> 
> **AKA**
> there exists a set $C$ and a function $f_R: B \to C$ s.t.
> $$\begin{aligned}
>     bRc \equiv f_R(b) = f_R(c)
> \end{aligned}$$

# Equivalence Classes
![](/images/20221206160852.png)

#### Example
Let $R$ be the equivalence relation of $\mod 5$.
$$\begin{aligned}
    aRb &\equiv a = b \pmod 5 \\
    [b]_R  &\equiv \{a \in \mathbb{N} \mid a = b \pmod 5\}
\end{aligned}$$
$$\begin{aligned}
    [3]_R &= \{3, 8, 13, 18, ...\}
\end{aligned}$$

# Properties of Equivalence Classes
![](/images/20221206161258.png)

![](/images/20221206161924.png)

> ***Notation***
> Let $R \subseteq$ be an equivlanece relation. The set of all equivalence classes of $R$ is denoted by $B\setminus_R$
> $$\begin{aligned}
>     B\setminus_R =\{[b]\mid b\in B\}
> \end{aligned}$$

![](/images/20221206163056.png)

> ***Definition***
> A binary relation $R$ on a set $B$ is called a *partial order* on $B$ if it is reflexive, antisymmetric, and transitive.
> - antisymmetric - $bRc \land cRb \Rightarrow b = c$
> 
> In this case, $(B, R)$ is a ***partially ordered set*** or ***poset***
- $\preceq$ - arbitrary partial order

![](/images/20221206164057.png)

# Strict/Sharp Partial Orders
> ***Definition***
> Relation $\prec$ is a ***quasi*** order or ***strict/sharp partial order*** if $\prec$ is irreflextive and transtive, i.e.
> $$\begin{aligned}
>     b \not \prec b \land (b \prec c \prec d \Rightarrow b \prec d)
> \end{aligned}$$
> - basically a partial order but without the equals sign. 
> - Not antisymmetric since this allows for equality

![](/images/20221206172700.png)
- $\setminus$ is used as removing elements from a set here, not as the set of all equivalence classes.

# Total/Linear Orders
![](/images/20221206164455.png)

# Stratified/Weak Orders
![](/images/20221206164807.png)

![](/images/20221206170049.png)

![](/images/20221206182553.png)


# Well-founded sets and partial orders
> ***Recall***
> - Element $y$ is a minimal element $S$ *iff* $y \in S$ and $(\forall x \mid x \prec y: x \not \in S)$

![](/images/20221206183052.png)

# Lower/Upper Bounds
![](/images/20221206183726.png)
- sets may have more than one minimal element, but there is always at most one least element
    - **Example**: A straightforward example is to consider all pairs $(a,b)$ of non-negative integers and order them by $(a,b) < (c,d)$ if and only if $a<c \land b<d$. Then all elements on the x-axis and y-axis are minimal (i.e. elements of the form (a,0) or (0,b) are minimal, since if something is less than 0 it would not be in S).
- minimal elements and least elements of a set belong to the set
- Lower bounds need not belong to the set

![](/images/20221206185255.png)
Basically the same thing as lower definition.

![](/images/20221206185703.png)

![](/images/20221206185725.png)

# Fixed Points
> ***Terminology***
> Upper and lower bounds createe a foundations of a special class of partial partial orders called ***latices***.
> 
> Lattice theory is a foundation of a theory of ***fixed points***, i.e. finding solutions to the equations $F(x) = x$, where $F: X \to X$ and $X$ is some set.

# Lattices
![](/images/20221206190339.png)
- yeah the visualization's lost on me.

# Monotone Functions
![](/images/20221206203543.png)
![](/images/20221206203559.png)

![](/images/20221206211628.png)

# Lattice of Relations
![](/images/20221206212209.png)

![](/images/20221206212301.png)

![](/images/20221206212434.png)

# While $T$ do $S$ od
![](/images/20221206212943.png)

![](/images/20221206212956.png)

# Interval Orders
![](/images/20221206213040.png)

![](/images/20221206213215.png)
- $b(a)$ - the beginning of interval $a$
- $e(a)$ - the end of interval $a$


