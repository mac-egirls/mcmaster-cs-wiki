---
title: 3 - propositional calculus.md
description: 
published: true
date: 2023-09-05T18:00:28.278Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:00:25.257Z
---

> ***Definitions***
> *calculus* - method or process of reasoning by calculation with symbols
> *propositional calculus/equational logic/__E__* - method of calculating with boolean expressions with propositional variables

> ***Inference rules***
> ![](/images/20220915170548.png)

> ***Theorem***
> 1) an axiom
> 2) The conclusion of an inference rule whose premises are theorems
> 3) a boolean expression that, using the inference rules, is proved equal to an axiom or a previously proved theorem.

# Equivalence and true

## Axioms
 ![](/images/20220915171410.png)
 
 ![](/images/20220915171423.png)

> ***Prove $p \equiv p \equiv q \equiv q$***
> ![](/images/20220915171947.png)

![](/images/20220915172023.png)

### Prove:
![](/images/20220915172250.png)

#### 3.4)
![](/images/20220915172920.png)

#### 3.5)
$$\begin{aligned}
	true \equiv p \equiv p 
& & \text{\footnotesize(Axiom 3.3)}\end{aligned}$$

# Negation, Inequivalence, and false
![](/images/20220915173434.png)
![](/images/20220915173630.png)

## Proof Heuristics and Principles

> ***Definition of **Heuristic*****
> **Heuristic** - identify applicable theorems by matching the structure of expression or subexpressions. The operators that appear in a boolean expression and the shape of its subexpressions can focus the choice of theorems to be used in manipulating it.
> **Heuristic of Definition Elimination** - To prove a theorem concerning an operator $\circ$  that is defined in terms of another, say $\bullet$, expand the definition of $\circ$ to arrive at a formula that contains $\bullet$; exploit properties of $\bullet$ to manipulate the formula; and then (possibly) reintroduce $\circ$ using its definition

# Disjunction
![](/images/20220915174810.png)

![](/images/20220915174940.png)

# Conjunction
![](/images/20220915175236.png)
![](/images/20220915175352.png)
![](/images/20220915175416.png)
![](/images/20220915175509.png)
![](/images/20220915175521.png)
![](/images/20220915175539.png)

# Implication
![](/images/20220924192126.png)
![](/images/20220924192136.png)
![](/images/20220924192158.png)
![](/images/20220924192208.png)
![](/images/20220924192217.png)
![](/images/20220924192225.png)
![](/images/20220924192234.png)

![](/images/20220924192316.png)
![](/images/20220926003044.png)
Different from *Inference rule Leibniz*, which describes that all $X=Y$ must be valid.

![](/images/20220924192255.png)
![](/images/20220924192335.png)

> ***Proof***
> ![](/images/20220926002025.png)
