---
title: 37 - Regression Diagnostic.md
description:
published: false
date: 2023-07-03 00:49:52.991488
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.991490
---

# Diagnostics
> ***Diagnostics for a good model***
> We would like $\epsilon$ to have a small variance

- Low noise variance = good
    - if the fit is good and low noise, hope for good prediction value.

$\hat \beta_0, \hat \beta_1$ are estimates for $\beta_0, \beta_1$ unknown. Props have $\sigma^2$ unknown but have estimates so can compute standard error. By properties of $\hat \beta_1, \hat \beta_0$, we have
$$\begin{aligned}
    E[\hat \beta_1] = \beta_1, E[\hat \beta_0] = \beta_0
\end{aligned}$$
and
$$\begin{aligned}
    Var(\hat \beta_1)
    &=
        \frac{\sigma^2}{S_{xx}} 
    & & \text{\footnotesize($\sigma^2 = Var(\epsilon)$)}\\ \\
    Var(\hat \beta_0)
    &=
        \sigma^2 \left(\frac{1}{n}+ \frac{x^{-2}}{S_{xx}}\right)
\end{aligned}$$

Since we have an estimator for $\sigma^2$, we can give a standard error for $\hat \beta_1$ as
$$\begin{aligned}
    SE(\hat \beta_1)
    &=
        \sqrt\frac{\hat \sigma^2}{S_{xx}}
    \\&= 
        \sqrt{\frac{\sum_{i=1}^n(y_i - \hat y_i)^2}{(n-2)\sum_{i=1}^n(x_i^2-n\overline{x}^2)}}
& & \text{\footnotesize(want as small as possible)}\end{aligned}$$

*Notice* if the model is a good fit this should shrink as $n$ gets large.

# Linear Regression
Super important assumption: $\epsilon \sim N(0, \sigma^2)$.

#### Simplified Situation
- have $x_1, \dots, x_n \leftarrow$ data from some distribution
- $y_i = \beta_0 + \beta_1 x_i + \epsilon_i$
    - $\epsilon_i \sim N(0, \sigma^2)$
- *So* $y_i \sim N(\beta_0 + \beta_1 x_i, \sigma^2)$
- We get paired data
$$\begin{aligned}
    \{ (x_i, y_i) \}
\end{aligned}$$
- Want to perform tests on $\beta_0, \beta_1$

Let $\beta_{1,0} \in \mathbb{R}$.
Set up a test:
$$\begin{aligned}
    H_0&: \beta_1 = \beta_{1, 0} \\
    H_1&: \beta_1 \ne \beta_{1, 0} 
& & \text{\footnotesize(or one-sided alternative)}\end{aligned}$$
By our assumption that $\epsilon \sim N(0, \sigma^2)$, we get that
$$\begin{aligned}
    \hat \beta_1
    &=
        \frac{\sum_{i=1}^n x_i Y_i - n \overline x \overline Y}{\sum_{i=1}^nx_i^2-n\overline{x}}
\end{aligned}$$
- linear combo of normal RV's so its normal!
$$\begin{aligned}
    \hat \beta_1 \sim N\left(\beta_1, \frac{\sigma^2}{S_{xx}}\right)
\end{aligned}$$
*So* to perform this test, we can choose as a test stat
$$\begin{aligned}
    T_0
    &=
        \frac{\hat \beta_1 - \beta_{1,0}}{\sqrt{\dfrac{\hat \sigma^2}{S_{xx}}}}
\end{aligned}$$
- has a $t$-distribution with $n-2$ degrees of freedom *iff* $H_0$ is true.

*Proceed as usual*: given some $\alpha$, reject $H_0$ *iff*
$$\begin{aligned}
    |t_0| &> t_{\frac{\alpha}{2}, n-2} \\
    \text{p-value} &< \alpha
\end{aligned}$$

> ***Test for $\beta_0$ and $\beta_1$***
> **$\beta_1$**
> $$\begin{aligned}
>     T_0
>     &=
>         \frac{\hat \beta_1 - \beta_{1,0}}{\sqrt{\dfrac{\hat \sigma^2}{S_{xx}}}}
> \end{aligned}$$
> 
> **$\beta_0$**
> $$\begin{aligned}
>     T_0
>     &=
>         \frac{\hat \beta_0 - \beta_{1,0}}{\sqrt{\hat \sigma^2\left(\frac{1}{n} + \frac{\overline x^2}{S_{xx}}\right)}}
> \end{aligned}$$

#### Back to $\beta_1$
How can we decide if there is actually a linear relationship between $X$ and $Y$?
Imagine there is *no* linear relation


![](/images/20230702003123.png)

So we can test for this!

#### Test
$$\begin{aligned}
    H_0&: \beta_1 = 0 \\
    H_1&: \beta_1 \ne 0
\end{aligned}$$
- $H_0$ - suggests no linear relationship
- $H_1$ - suggests possible linear relationship

In the situation where we accept $H_0$ our conclusion should be that either there is no  relation between $X$ and $Y$ *or* there is a non-linear relationship and a linear model is *not* predictive.


![](/images/20230702003136.png)

# $R^2$
Assuming a model
$$\begin{aligned}
    Y = \beta_0 + \beta_1 X + \epsilon
\end{aligned}$$

Given some data $\{x_1, y_1), \dots, (x_n, y_n)\}$
- least squares estimates: $\hat \beta_0 \hat \beta_1$
- Observed values: $y_1, \dots, y_n$
- Predicted values: $\hat y_i = \hat \beta_0 + \hat \beta_1 x_i$

![](/images/20230702003156.png)

$$\begin{aligned}
    e_i &= y_i - \hat y_i \\
    SS_T &= \sum_{i=1}^n (y_i - \overline y)^2 \\
    SS_R &= \sum_{i=1}^n (\hat y_i - \overline y)^2 \\
    SS_T &= SS_R + SS_E
\end{aligned}$$
- $SS_T$ - measure of *variation* observed in the response data $y$
- $SS_R$ - measure of  the *variation* predicted by the regression

**Naively**
The model is good if the observed variation in the response variable is explained

> ***Define***
> $$\begin{aligned}
>     R^2
>     &=
>         \frac{SS_R}{SS_T} = 1 - \frac{SS_E}{SS_T}
> \end{aligned}$$
> - meant to be the proportion of total variation accounted for by the regression model.
> - *Observe*: if the regression model perfectly predicts the response variable i.e. $\hat y_i = y_i$ for all $i$, then
> $$\begin{aligned}
>     R^2 &= \frac{\sum_{i=1}^n (\hat y_i - \overline y)^2}{\sum_{i=1}^n (y_i - \overline y)^2} = 1
> \end{aligned}$$

**Naively**
If $R^2 \sim 1$, then the model is probably pretty good.

> ***warning***
> - Without context $R^2$ can be misleading.
> - In simple linear regression, $R^2$ is a pretty good diagnostic.


![](/images/20230702003212.png)


