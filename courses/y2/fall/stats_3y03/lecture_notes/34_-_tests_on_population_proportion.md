---
title: 34 - tests on population proportion.md
description:
published: false
date: 2023-07-02 19:22:47.758844
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.758845
---

2022-11-24

# Review of Hypothesis Tests on the mean of a normal distribution, variance unknown
- If sample size $n$ is large *($\ge 40$)* can do a $z$-test.
- If $n$ is not big, can do a $t$-test.

$$\begin{aligned}
    H_0&: \mu = \mu_0 \\
\end{aligned}$$
- Choose $T_0 = \frac{X-\mu_0}{\frac{s}{\sqrt{n}}}$ has a $t_{n-1}$ distribution iff $H_0$ is true.

*process*
Choose $\alpha \in (0, 1)$ our confidence level. Collect data, compute $t_0$
1. $H_1: \mu \ne \mu_0$, reject $H_0$ *iff* $|t_0| > t_{\frac{\alpha}{2}, n-1}$ *iff* $\alpha > 2P(t_{n-1} > |t_0|)$ - $p$-value.
2. $H_1: \mu > \mu_0$, reject $H_0$ *iff* $t_0 > t_{\alpha, n-1}$ *iff* $\alpha > P(t_{n-1} > t_0)$
3. $H_1: \mu<\mu_0$, reject $H_0$ *iff* $t_0 < -t_{\alpha, n-1}$ *iff* $\alpha > P(t_0 < t_{n-1})$

#### Example
Suppose we want to test the average grade on test 2.
$$\begin{aligned}
    H_0&: \mu = 70 \\
    H_1&: \mu > 70 \leftarrow \text{ alternate is the true mean is higher  than 70}
\end{aligned}$$

*Pick some $\alpha$*: $(1 - \alpha = 0.98)$
Let's take a small sample of 10 people.
$$\begin{aligned}
    T_0 &= \frac{\overline X - 70}{\frac{s}{\sqrt{10}}} \\
\end{aligned}$$

Say we find $\overline X = 55, s = \sqrt{10}$ Then,
$$\begin{aligned}
    t_0 = 55 - 70 = -15
\end{aligned}$$

This is very extreme. *But* since $H_1: \mu > 70$, we have insufficient evidence to lead to a rejection of $H_0$.

##### $t_\alpha$ distribution assuming $H_0$ is true.

![](/images/20230702003854.png)

- \* - $P$-value for upper tailed $t-test$ is $P(t_\alpha > t_0)$
    - $P(t_\alpha > -15) > 0.5$
So $p$-value of $t_0 = -15 > (\alpha = 0.01)$ *so* we cannot reject $H_0$

# Tests on Population Proportion
- Suppose we are interested in some population with a particular subset that corresponds to proportion $p$ of the total.
    - what proportion of all engineering students are female?

- Suppose we take a sample of size $n$.
- Let $X = \#$ of samples from the subclass $X \sim Bin(n, p)$ - $p$ is unknown
- $\hat P = \frac{X}{n}$ - unbiased estimator for $p$
- We know $np > S$ and $n(1-p) > s$, then $X \approx N(np, np(1-p))$.

Let's set up a test.
$H_0: p = p_0$ - some number
$H_1: p \ne p_0\ \lor p > p_0 \lor p<p_0$
Fix a sig level $\alpha$. $H_0$ is *true* 
- *iff* $X \approx N(np_0, np-0(1 - p_0))$ 
- *iff* $\hat P = \frac{X}{n} \approx N(p_0, \frac{p_0(1 - p_0)}{n})$

Choose a test statistic by standardizing:
$$\begin{aligned}
    Z_0 = \frac{\hat P - p_0}{\sqrt{\frac{p_0(1-p_0)}{n}}}
\end{aligned}$$

Then $H_0$ is *true* *iff* $Z_0 \approx N(0, 1)$.
Suppose we collect some data and find $Z_0 = z_0$. Then,
1. $H_1: p \ne p_0$, reject $H_0$ 
    - *iff* $|z_0| \ge z_{\frac{\alpha}{2}}$
    - *iff* $\alpha > 2P(Z \ge |z_0|)$
2. $H_1: p>p_0$, reject $H_0$
    - *iff* $z_0 > z_\alpha$
    - *iff* $\alpha > P(Z > z_0)$ - p-value
3. $H_1: p<p_0$, reject $H_0$
    - *iff* $z_0 < -z_\alpha$
    - *iff* $\alpha > P(Z < z_0)$
    
#### Example
In 2018, McMaster claimed that $27\%$ of all incoming engineering students were female.
$$\begin{aligned}
    H_0&: p = 0.27 \\
    H_1&: p \ne 0.27
\end{aligned}$$
at $99\%$ confidence. In a sample of 46 engineers, there were 12 female engineers. *So*
$$\begin{aligned}
    \hat P &= \frac{10}{46} = 0.217 \\
    \\
    z_0 &= \frac{0.217 - 0.27}{\sqrt{\frac{0.27(1-0.27)}{46}}} \\
    &= -0.81
\end{aligned}$$

**2-sided $p$-value**
$$\begin{aligned}
    2P(Z > |-0.81|) &= 1.58226
\end{aligned}$$
