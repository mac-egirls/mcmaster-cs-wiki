---
title: 8 - programming and hoare logic.md
description: 
published: true
date: 2023-09-05T18:00:56.914Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:00:52.972Z
---

![](/images/20221031175235.png)

- ***Precondition*** - assertion about variables when the statement can be executed
- ***Postcondition*** - assertion about variables when the statement terminates

#### Example
![](/images/20221031180646.png)

# Reasoning about the assignment statement
Just look at [definition of assignment](/courses/y2/fall/compsci_2lc3/lecture_notes/8_-_programming_and_hoare_logic.md)

- The final state is not always unambiguously determined.
$$\begin{aligned}
    \{true\}\ b:=?\ \{b^2 = 25\}
\end{aligned}$$
- ? - there are many expressions that lead to the postcondition
- Above, $b = -5, 5$ could work

> ***$dom(E)$***
> We have
> $$\begin{aligned}
>     \{R[x := E]\} x := E \{R\}
> \end{aligned}$$
> 
> For each expression $E$,  $dom(E)$ is satisifed in exactly those states in which $E$ is defined.
> Basically the *domain* of $E$.
> 
> More generally, assignment is
> $$\begin{aligned}
>     \{dom(E) \land R[x := E]\}\ x:=E\ \{R\}
> \end{aligned}$$

![](/images/20221101003424.png)

> ***Weakest Precondition***
> - $R[X:=E]$ - the *weakest precondition*
> - To show that $x := E$ is an implementation of $\{Q\}\ x := ?\ \{R\}$ prove $Q \Rightarrow R[x := E]$ holds.

Find the weakest precondition such that
$$\begin{aligned}
    \{?\}\ x &:= E; y := F\ \{R\} \\
    \{?\}\ x &:= E; \{R[y := F]\}\ y := F\ \{R\} \\
    \{R[y := F][x := E]\}\ x &:= E;\ \{R[y := F]\}\ y := F\ \{R\}
\end{aligned}$$
- $\{R[y:=F]\}$ is a postcondition to $y$ using the [Definition of Assignment](/courses/y2/fall/compsci_2lc3/lecture_notes/8_-_programming_and_hoare_logic.md)
- The postcondition of $y$ is precondition of $x$

> ***Weakest Precondition of $n$ assignments***
> $$\begin{aligned}
>     \{R[x_n := E_n] \cdots [x_a := E_a]\}\ x_1 := E_1; \cdots x_n := E_n\ \{R\}
> \end{aligned}$$

#### Example
![](/images/20221101104643.png)

# Calculating Parts of Assignments
Consider
$$\begin{aligned}
    P1: x = \left(\sum k | 0 \le k < i: b[k]\right)
\end{aligned}$$
Solve for $e$ in
$$\begin{aligned}
    \{P1\}\ i, x := i+1, e\ \{P1\}
\end{aligned}$$
Prove that the precondition implies the post condition to get $e$

![](/images/20221101105405.png)

# Conditional Statements and Expressions
> ***Notation***
> ![](/images/20221101110403.png)
> - $S_1, S_2$ - statements
![](/images/20221101110506.png)

> ***Alternative Notation***
> ![](/images/20221101110702.png)
> 
> - $B \to S$ - a *guarded command*
> - $B$ - the guard
> - Execution aborts if no guard is *true*
>     - ***abort*** - terminte prematurely. Undefined behaviour.
> - If $\ge 1$ guard is true, only one is chosen (arbitrarily)
>     - Called ***nondeterministic***

#### Example
![](/images/20221101111152.png)
- doesn't matter which of $x$ and $y$ is stored in $z$ when $x = y$
- nondeterministic alternative statements help programmers not struggle with a choice

> ***Proof for $IFG$***
> - $IFG$ - alternative statement with 3 guards.
> ![](/images/20221101111607.png)

## Conditional expression
[Conditional Statements](/courses/y2/fall/compsci_2lc3/lecture_notes/8_-_programming_and_hoare_logic.md) but with expressions instead of statements.
![](/images/20221101112327.png)

# Loops
![](/images/20221101111940.png)

#### Example
![](/images/20221101112001.png)

# Hoare Logic
![](/images/20221101112404.png)
![](/images/20221101112412.png)