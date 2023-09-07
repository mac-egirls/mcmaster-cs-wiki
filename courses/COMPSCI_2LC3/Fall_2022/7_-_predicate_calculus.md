---
title: 7 - predicate calculus.md
description: 
published: true
date: 2023-09-05T18:00:47.319Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:00:43.931Z
---

- *predicate calculus formula* - boolean expression with some boolean variables may have been replaced by
    - *predicates*: applications of boolean functions whose arguments could be types other than $\mathbb{B}$
    - *Universal* and *existential quantification*

# Axioms
![](/images/20221007130012.png)

## Universal Quantification
$$\land (x \mid R : P) := \forall (x \mid R : P)$$
![](/images/20221024121515.png)
![](/images/20221024121831.png)
==NOTE:== (9.6) is ***distributivity of $\lor$ over $\forall$***

> ***distributivity of $\land$ over $\forall$***
> A conjunct can be moved outside the scope of the quantification only if  the range $R$ is not $false$ everywhere.
> 
> If $R$ is $false$, then
> $$\begin{aligned}
>     (\forall x | R: P \land Q)
>     &\equiv
>         (\forall x | false: P \land Q)
>     \\&\equiv 
>         true
> & & \text{\footnotesize(Empty Range)}\end{aligned}$$
> 
> But
> $$\begin{aligned}
>     P \land (\forall x | R: Q)
>     &\equiv
>         P \land (\forall x | false: Q)
>     \\&\equiv 
>         P \land true
>     & & \text{\footnotesize(Empty Range)}\\&\equiv 
>         P
> & & \text{\footnotesize(Identity)}\end{aligned}$$

![](/images/20221024122152.png)
![](/images/20221024151651.png)

## Existential Quantification
$$\lor(x \mid R:P) := \exists (x \mid R : P)$$
- A value $\hat x$ for which $(R \land P)[x := \hat x]$ is valid is called a *witness for $x$ in $\exists(x \mid R:P)$.
![](/images/20221024134618.png)
![](/images/20221024134748.png)
![](/images/20221024134808.png)

![](/images/20221024134822.png)

![](/images/20221024134849.png)
![](/images/20221024134931.png)

![](/images/20221024151858.png)
![](/images/20221024151847.png)
