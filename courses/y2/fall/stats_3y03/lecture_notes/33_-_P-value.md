---
title: 33 - P-value.md
description: 
published: true
date: 2023-07-03T00:29:06.241Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:29:01.783Z
---

- Fix a significance level $\alpha$.
- Fixing a determine the size of our critical region

> ***Definition***
> Suppose we know a test with $H_0$. The ***p-value*** of the data is the smallest significance level that would lead to a rejection of $H_0$.
> 
> - *Picture* - $H_0: \theta = \theta_0$
> - *Two-sided picture*
> 
> 
> ![](/images/20230702002723.png)

#### Example
Sample a normal distribution $N(\mu, 10^2)$, $n = 35$
$$\begin{aligned}
    H_0&: \mu = 50 \\
\end{aligned}$$

Say we find $\overline x = 54$ (observed data). Find the p-value if
1. $H_1:\mu \ne 50$

![](/images/20230702002747.png)
    thus to get a rejection of $H_0$, the critical region would have to be (46, 54). So the p-value is the significance of this CR:
$$\begin{aligned}
    \alpha &= P(\text{rejecting $H_0$ | $H_0$ is true})
    \\&=
        P\left(\overline X > 54 \text{ or } \overline X < 46 \mid \overline X \sim N\left(50, \frac{100}{35}\right)\right)
    \\&=
        0.018
\end{aligned}$$

# Relationship to CI's
- Suppose $[L, U]$
- *Then* a hypothesis test of significance level $\alpha(=P(\text{Rejecting } H_0 \mid H_0 \text{ is true}))$

Leads to a rejection of $H_0$ iff
$$\begin{aligned}
    r \notin [L, U]
\end{aligned}$$
- In *other words* a $100(1 - \alpha)\%$ CI is exactly the critical region for a hypothesis test of confidence level $\alpha$.
- Upper/lower CIs then correspond to upper/lower tailed tests.

![](/images/20230702002813.png)
Reject $H_0$ iff p-value $< \alpha$.
Test on mean of normal distribution of variance known.
Let's fix a null hyp:
$$\begin{aligned}
    H_0: \mu = \mu_0
\end{aligned}$$

We have 3 cases for $H_1$
$$\begin{aligned}
    H_1: \mu \ne \mu_0, \mu > \mu_0, \mu < \mu_0
\end{aligned}$$
Use $\overline X$ to estimate $\mu$.
- standardize to get $\frac{\overline X - \mu_0}{\frac{\sigma}{\sqrt{n}}}$

> ***important***
> $$\begin{aligned}
>     \frac{\overline X - \mu_0}{\frac{\sigma}{\sqrt{n}}} \sim N(0, 1)
> \end{aligned}$$
> iff $H_0$ is true.
> 
> If $H_0$ is not true, then $E[\overline X] \ne \mu_0$ so $E\left[\frac{\overline X - \mu_0}{\frac{\sigma}{\sqrt{n}}}\right] \ne 0$ so $E\left[\frac{\overline X - \mu_0}{\frac{\sigma}{\sqrt{n}}}\right] \not \sim N(0, 1)$
> 
> Terminology: Any test of this form is called a Z-test.

Structure of a Z-test with significance level $\alpha$.
- Choose a significance level $\alpha$.
1. From some data, compute a value of our ***test statistic***.
$$\begin{aligned}
    z_0 = \frac{\overline x - \mu_0}{\frac{\sigma}{\sqrt{n}}}
\end{aligned}$$
2. Find the p-value of $z_0$
3. Reject $H_0$ iff p-value of $z_0 \le \alpha$ 

![](/images/20221201142919.png)

![](/images/20221202140359.png)

- The critical value is the value being checked against $z_0$ or $t_0$.

## Case I: $\mu \ne \mu_0$

![](/images/20230702002855.png)
$$\begin{aligned}
    \text{p-value of $z_0$}
    &=
        2P(Z \le -|z_0|)
    \\&=
        2P(Z > |z_0|)
    \\&=
        2(1 - P(Z \le |z_0|))
    \\&=
        2 - 2P(Z \le |z_0|)
\end{aligned}$$

- So reject $H_0$ *iff*
$$\begin{aligned}
    \alpha &\ge 2(1 - P(Z \le |z_0|)) \\
    \frac{\alpha}{2} &\ge 1 - P(Z \le |z_0|) \\
    P(Z \le |z_0|) &\ge 1 - \frac{\alpha}{2} \\
    z_{\frac{\alpha}{2}} &< |z_0|
\end{aligned}$$
*So* the critical region of the $Z$ test is
$$\begin{aligned}
    [ -z_{\frac{\alpha}{2}}, z_{\frac{\alpha}{2}} ]
\end{aligned}$$
i.e. if we collect data and compute $z_0 = \frac{\overline x - \mu_0}{\frac{\sigma}{\sqrt{n}}}$ then reject $H_0$ *iff*
$$\begin{aligned}
    z_0 \notin [-z_{\frac{\alpha}{2}}, z_{\frac{\alpha}{2}} ]
\end{aligned}$$

*Probability better*: compute the p-values of $z_0$ and compare to $\alpha$.
- *p-value* gives an idea of how extreme your data is.

## Case II: $H_1: \mu > \mu_0$

![](/images/20230702002911.png)
If $H_1$ is true, we expect $z_0$ to skew to the right.
$$\begin{aligned}
    \text{P-value of $z_0$}
    &=
        P(Z \ge z_0)
    \\&=
        1 - P(Z < z_0)
    \\&=
        1 - \Phi(z_0)
\end{aligned}$$
Reject $H_0$
- *iff* p-value $<\alpha$
- *iff* $z_0 \ge z_\alpha$

### Strange ***TODO***
- even though it is is extreme, we would not reject $H_0$ if $H_1: \mu > \mu_0$

## Case III: Lower tail $H_1: \mu<\mu_0$

![](/images/20230702002939.png)
$$\begin{aligned}
    \text{p-value of $z_0$}
    &=
        P(Z \le z_0)
    \\&=
        \Phi(z_0)
\end{aligned}$$

Reject $H_0$ 
- *iff* p-value of $z_0 < \alpha$
- *iff* $z_0 < -z_\alpha$


