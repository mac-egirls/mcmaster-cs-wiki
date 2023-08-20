---
title: 36 - linear regression.md
description:
published: false
date: 2023-07-02 19:22:47.757230
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.757232
---

### Idea
Suppose we are given two RVs $X$ and $Y$.
- want to *assume* some sort of linear relationship.
$$\begin{aligned}
    Y = \beta_0 + \beta_1 X + \epsilon
\end{aligned}$$
- $\epsilon$ is the error term usually $E[\epsilon] = 0$
    - Usually assumed $\epsilon \sim N(0, \sigma^2)$
- Regardless of whether this is a good model, we want to try to estimate $\beta_0$ and $\beta_1$ (later we can check if the model is good).
    - $\beta_0, \beta_1$ are called ***regression coefficients***

> ***note***
> $$\begin{aligned}
>     E[Y]
>     &=
>         E[\beta_0 + \beta_1 X + \epsilon]
>     \\&=
>         \beta_0 + \beta_1E[X]
> \end{aligned}$$

- Suppose we sample the random vector $(X, Y)$.
    - Get some paired data
$$\begin{aligned}
    \{(x_1, y_1), \dots, (x_n, y_n)\}
\end{aligned}$$
- we want to use the sample to estimate the parameters $\beta_0, \beta_1$.
- Suppose we have a hypothetical line $y = \beta_0 + \beta_1x$
    - Think of $\beta_0$, $\beta_1$ as being allowed to vary.

![](/images/20230702003622.png)
> Equation of line: $y = \beta_0 + \beta_1x$
> \*$e_i = y_i - (\beta_0 + \beta_1x_i)$

- Can think of $e_i$ as a value of $\epsilon$, or a ***residual***

#### Strategy
Adjust $\beta_0$ and $\beta_1$ until it fits the data $\{x_1, y_1), \dots, (x_n, y_n)\}$ as best as possible.

> ***Idea: (Gauss)***
> Minimize the sum of the squares of the error:
> $$\begin{aligned}
>     F(\beta_0, \beta_1)
>     &=
>         \sum_{i=1}^n e_i^2
>     \\&=
>         \sum_{i=1}^n (y_i - \beta_0 - \beta_1x_i)^2
> \end{aligned}$$
> 
> From calculus, we know that the local extreme occurs when
> $$\begin{aligned}
>     \frac{\delta F}{\delta\beta_0} = 0 =  \frac{\delta F}{\delta\beta_1}
> \end{aligned}$$
> 
> $$\begin{aligned}
>     \begin{cases*}
>         \dfrac{\delta F}{\delta\beta_0} = 0 \\
>         \dfrac{\delta F}{\delta\beta_1} = 0
>     \end{cases*}
> \end{aligned}$$

> ***Least Squares Estimates***
> - So by linear algebra, there is always a solution
> - The estimators for $\beta_0, \beta_1$ are called the ***least squares estimates***.
> $$\begin{aligned}
>     \hat \beta_1
>     &=
>         \frac{
>             \sum_{i=1}^n x_i y_i - n \overline x \overline y
>         }{
>             \sum_{i=1}^n x_i^2 - n \overline x^2
>         }
>     \\&=
>         \frac{S_{xy}}{S_{xx}}
>     \\ \\
>     \hat \beta_0 &= \overline y - \hat \beta_1 \overline x
> \end{aligned}$$

#### Example
Consider the data
$$\begin{aligned}
    \{(1, 2), (2,5), (3,3), (4,8), (5,7)\}
\end{aligned}$$
| $i$  | $x_i$ | $y_i$ | $x_iy_i$ | $x_i^2$ |
| ---- | ----- | ----- | -------- | ------- |
| 1    | 1     | 2     | 2        | 1       |
| 2    | 2     | 5     | 10       | 4       |
| 3    | 3     | 3     | 9        | 9       |
| 4    | 4     | 8     | 32       | 16      |
| 5    | 5     | 7     | 35       | 25      |
| sum  | 15    | 25    | 88       | 55      |
| mean | 3     | 5      |          |         |

$$\begin{aligned}
    \hat \beta_1
    &=
        \frac{88-5(3)(5)}{55-5(3)^2}
    \\&=
        \frac{13}{10}
    \\&=
        1.3
    \\ \\
    \hat \beta_0
    &=
        \overline y - \hat \beta_1 \overline x
    \\&=
        5 - (1.3)(3)
    \\&=
        1.1
\end{aligned}$$

*So* the line of best fit is
$$\begin{aligned}
    y = 1.1 + 1.3x
\end{aligned}$$
Predict the value of $Y$ for $X = 6$
$$\begin{aligned}
    y = 1.1 + 1.3(6) = 8.9
\end{aligned}$$

- Constructing a linear model is fine, but we want some techniques for determining of our model is good/useful.

**Imagine two scenarios:**

![](/images/20230702003656.png)
- A good diagnostic tool is an estimate for the error/noise term in the linear model.
$$\begin{aligned}
    Y = \beta_0 + \beta_1 X + \epsilon
\end{aligned}$$

> ***Estimate $Var(\epsilon) = \sigma^2$***
> $$\begin{aligned}
>     SS_E &=
>         \sum_{i=1}^n(y_i - \hat y_i)^2
>     \\ \\
>     \hat \sigma^2 
>     &= \frac{SS_E}{n-2}
>     \\&=
>         \frac{\sum_{i=1}^n(y_i - \hat y_i)^2}{n-2}
>     \\&=
>         \frac{\sum_{i=1}^n(y_i - (\hat \beta_0 + \hat \beta_1x_i))^2}{n-2}
> \end{aligned}$$
> 

> ***shortcut to compute $SS_E$***
> $$\begin{aligned}
>     SS_E &= SS_{Total} - SS_{Regression}
> \end{aligned}$$
> - $SS_T$ - total sum of square
> - $SS_R$ - regression sum of square
> 
> Where 
> $$\begin{aligned}
>   SS_T = SS_y = \sum_{i=1}^n y_i^2 - n \overline y^2
> \end{aligned}$$
> measures the total variance in the data
> $$\begin{aligned}
>     SS_R &= \hat \beta_1 S_{xy}
>     \\&=
>         \hat \beta_1 \left(\sum_{i=1}^n x_i y_i - n \overline x \overline y\right)
> \end{aligned}$$
> - meansuring the variance attributed to the linear model.
> 
> *So* $SS_T - SS_R$ should be a measure of the variance supplied by the noice term $\epsilon$.

#### Example
$$\begin{aligned}
    SS_T
    &=
        2^2 + 5^2 + 3^2 + 8^2 + 7^2 - 5(5)^2
    \\&=
        26
    \\ \\
    S_R
    &=
        (1.3) (88 - 5(3)(5))
    \\&=
        16.9
    \\ \\
    SS_E
    &=
        26 - 16.9
    \\&=
        9.1
    \\ \\
    \hat \sigma^2
    &=
        \frac{9.1}{5} < 2
\end{aligned}$$

