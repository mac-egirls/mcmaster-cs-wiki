---
title: 20 - Linear Functions of Random Variables.md
description: 
published: true
date: 2023-09-05T18:02:10.189Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:02:06.281Z
---

> ***Linear Combination***
> Given RVs $X_1, X_2, \dots, X_p$ and constants $c_1, c_2, \dots c_p$,
> $$\begin{aligned}
>     Y = c_1 X_1 + c_2 X_2 + \cdots + c_p X_p
> \end{aligned}$$
> is a ***linear combination*** of $X_1, X_2, \cdots X_p$

Then, find $E[Y]$:
$$\begin{aligned}
    E[Y]
    &=
        \int_{-\infty}^\infty
        \int_{-\infty}^\infty
        \cdots
        \int_{-\infty}^\infty
        (c_1x_1 + \cdots c_p x_p)
        f_{X_1, \dots X_p}
        (x_1, \dots, x_p)
        \ dx_1 \dots dx_p
    \\&=
        c_1
        \int_{-\infty}^\infty
        \int_{-\infty}^\infty
        \cdots
        \int_{-\infty}^\infty
        x_1 f_{X_1, \dots X_p}
        (x_1, \dots, x_p)
        \ dx_1 \dots dx_p
        \\&+
            c_2
            \int_{-\infty}^\infty
            \int_{-\infty}^\infty
            \cdots
            \int_{-\infty}^\infty
            x_2 f_{X_1, \dots X_p}
            (x_1, \dots, x_p)
            \ dx_1 \dots dx_p
        \\&+
            \cdots
        \\&+
            c_p
            \int_{-\infty}^\infty
            \int_{-\infty}^\infty
            \cdots
            \int_{-\infty}^\infty
            x_p f_{X_1, \dots X_p}
            (x_1, \dots, x_p)
            \ dx_1 \dots dx_p
\end{aligned}$$

> ***E[Y] and Var(Y)***
> $$\begin{aligned}
>     E[Y] &= c_1 E[X_1] + c_2 E[X_2] + \cdots + c_p E[X_p] \\
> \end{aligned}$$
> 
> If $X_1, \dots, X_p$ are **independent**, then
> $$\begin{aligned}
>     V(Y) &= c_1^2 V(X_1) + \cdots + c_p^2 V(X_p)
> \end{aligned}$$

# Mean and Variance of an Average
![](/images/20221030234754.png)

![](/images/20221030234936.png)

