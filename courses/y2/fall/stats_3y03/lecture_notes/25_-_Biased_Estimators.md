---
title: 25 - Biased Estimators.md
description:
published: false
date: 2023-07-03 00:49:52.991227
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.991231
---

- Technique for choosing an unbiased estimator:
![](/images/20221120003640.png)
- Thus minimize the variance

**minimum variance**:

![](/images/20230702003011.png)

**high variance**

![](/images/20230702003023.png)

> ***Definition***
> Let $\theta$ be a paramter. Then an estimator of $\theta$, $\hat \Theta$, with minimal variance is called the ***minimum variance unbiased estimator*** (MVUE) of $\theta$.

> ***Fact***
> If $X_1, \dots, X_n$ is a random sample of an RV $X$, then $\overline X$ (the average of the random sample) is the MVUE of $E[X]$.

- Another technique: consider the ***Error***
    - Error - standard dev. of estimator: $\sqrt{Var(\hat \Theta)}$
    - Sometimes we need to *further* estimator parameters (new ones) in $\sqrt{Var(\hat \Theta)}$
    - In that case, we estimate them (if possible) get a new estimator for $\sqrt{Var(\hat \Theta)}$, called ***standard error***, sometime $s_{\hat \Theta}$ or $SE(\hat \Theta)$ or $\hat \sigma_{\hat \Theta}$.

#### Example
Suppose we sample some data which we know is normal. Say we take sample size $n$. Say we want to estimate the true mean $\mu$.
- natural choice: $\overline X = \frac{1}{n}(X_1 + \cdots + X_n)$. $\overline X$ is normal and it's an unbiased estimator for $\mu$, so $E[\overline X] = \mu$.
- If $\sigma^2$ is the variance of the distribution we're sampling, then
$$\begin{aligned}
    \sigma^2_{\overline X} &= Var(\overline X) = \frac{\sigma^2}{n}, &\sigma_{\overline X} = \frac{\sigma}{\sqrt{n}}
\end{aligned}$$
- Typically, $\sigma^2$ is also unknown!!
    - So we need to further estimate $\sigma$ (we can estimate with the sample sample standard deviation $s$)
    - So, the standard error of $\overline X$ is $\hat \sigma_{\overline X} = \frac{s}{\sqrt{n}}$ (*won't show up that much 😩*)

# Biased Estimators

- Sometimes you cannot avoid introducing some bias
- One way to choose a good *BIASED* estimator is to minimize the ***mean square error***
- for $\hat \Theta$, the MSE is
$$\begin{aligned}
    MSE(\hat \Theta) &= E[(\hat \Theta - \theta)^2]
\end{aligned}$$

> ***Note***
> If $E[\hat \Theta] = \theta$ i.e., $\hat \Theta$ is unbiased then the ***mean square error*** is
> $$\begin{aligned}
>     MSE(\hat \Theta) &= E[(\hat \Theta - \theta)^2]
>     \\&= Var(\hat \Theta) + (E[\hat \Theta] - \theta)^2
> \end{aligned}$$

By algebra:
$$\begin{aligned}
    MSE(\hat \Theta)
    &=
        E[(\hat \Theta - E[\hat \Theta])^2] + (\theta - E[\hat \Theta])^2
    \\&=
        V(\hat \Theta) + (-(E[\hat \Theta] - \theta))^2
    \\&= 
        V(\hat \Theta) + (E[\hat \Theta] - \theta)^2
& & \text{\footnotesize($E[\hat \Theta] - \theta$ - the bias)}\end{aligned}$$

> ***biased estimators***
> If $\hat \Theta_1$ and $\hat \Theta_2$ are estimators for $\theta_1$ we say
> 
> $\hat \Theta_1$ is more efficient than $\hat \Theta_2$ iff
> $$\begin{aligned}
>     \frac{MSE(\hat \Theta_1)}{MSE(\hat \Theta_2)} < 1
> \end{aligned}$$
> 
> ##### Remark
> An estimator is called ***optimal*** if it's more efficient than another estimator.
> - optimal estimators rarely exist.
