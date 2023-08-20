---
title: 18 - independence on crv.md
description: 
published: true
date: 2023-07-03T00:27:48.788Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:27:45.537Z
---

$X, Y$ are continuous, with joint distribution $f_{X, y}(x, y)$. Then if $f_{XY}$ is 0 outside of a region $R$, then
$$\begin{aligned}
    f_X(x) &= \int_{R_Y(x)} f_{XY}(d, y)\ dy \\
    f_Y(y) &= \int_{R_X(y)} f_{XY}(x, y)\ dx
\end{aligned}$$

### Equivalently:

$$\begin{aligned}
    f_X(x) &= \int_{-\infty}^\infty f_{XY}(d, y)\ dy \\
    f_Y(y) &= \int_{-\infty}^\infty f_{XY}(x, y)\ dx
\end{aligned}$$

### Clear:
$$\begin{aligned}
    \int_{-\infty}^\infty f_X(x)\ dx = \int_{-\infty}^\infty \int_{-\infty}^\infty f_{XY}(x, y)\ dy\ dx = 1
\end{aligned}$$

> ***Definition***
> We say $X$ and $Y$ are *independent* CRV's iff
> $$\begin{aligned}
>     f_{XY}(x, y) &= f_X(x) f_Y(y)
> \end{aligned}$$
![](/images/20221030234622.png)

#### Example
Consider the uniform RV on the square $[0,2]^2$.
$$\begin{aligned}
    f_{XY}(x, y) &= \begin{cases*}
        \frac{1}{4}, (x, y) \in [0,2]^2 \\
        0, otherwise
    \end{cases*}
\end{aligned}$$
$$\begin{aligned}
    f_X(x) &= \begin{cases*}
        \frac{1}{2}, \text{ for } x \in [0,2] \\
        0, o/w
    \end{cases*} \\
    f_Y(y) &= \begin{cases*}
        \frac{1}{2}, \text{ for } y \in [0,2] \\
        0, o/w
    \end{cases*}
\end{aligned}$$

So
$$\begin{aligned}
    f_{XY}(x, y) &= f_X(x) f_Y(y)
\end{aligned}$$

So $X$ and $Y$ in this case are independent!

#### Non-Example
Consider the uniform distribution on the unit circle.
$$\begin{aligned}
    f_{XY}(x, y) &= \begin{cases*}
        \frac{1}{\pi}, x^2+y^2 \le 1 \\
        0, otherwise
    \end{cases*}
\end{aligned}$$
$$\begin{aligned}
    f_X(x) &= \begin{cases*}
        2 \sqrt{1-x^2}, x \in [-1, 1] \\
        0, otherwise
    \end{cases*} \\
    f_Y(Y) &= \begin{cases*}
        2 \sqrt{1 - y^2}, y \in [-1, 1] \\
        0, otherwise
    \end{cases*}
\end{aligned}$$
$$\begin{aligned}
    f_{XY} (x, y) &\ne f_X(x) f_Y(y)
\end{aligned}$$

> ***note***
> If $X$ and $Y$ are jointly distributed with $f_{XY}(x, y)$, and $X$ and $Y$ are independent, *then* $f_{XY}$ must be zero outside of a rectangular region $R = R_1 \times R_2$.
> 
> In otherwords, if $f_{XY}(x, y)$ is non-zero on a region which is not rectangular then $X$ and $Y$ are not independent.

#### Example
$X, Y$ s.t.
$$\begin{aligned}
    f_{XY}(x, y) &= \begin{cases*}
        \frac{x+y}{32}, 0 \le y \le x \le 4 \\
        0, o/w
    \end{cases*}
\end{aligned}$$

![](/images/20230702002506.png)

- triangle, not a rectangle. So $X, Y$ are not independent.

> ***warning***
> Converse rules, i.e. there are $X, Y$ with $f_{XY}\ne 0$ on a rectangular region, which still fail to be independent.
