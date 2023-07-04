---
title: 38 - single factor experiements and ANova.md
description:
published: false
date: 2023-07-03 00:49:52.990623
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.990628
---

2022-12-02

- In an experiment, a *factor* is a variable that the experimenter controls; the idea is to *vary* the factor to gain some knowledge over some ***response variable***.
- For us, we will assume that the factor can take finitely many values (called ***treatments***).

#### Example
- Symptoms - response variable
    - can vary the dosage of some new drug
        - Low dose
        - Med dose
        - High dose
- Academic performance - response
    - weekly exercise - factor
    - 0,1,2,..., 7 dates per week

Let's formalize this mathematically
- fix the number of treatments, $a = \#$ of treatments
- For the $i$th treatment, $(1 \le i \le a)$ get a random sample
$$\begin{aligned}
    Y_{i_1}, Y_{i_2}, \dots, Y_{i_{n_i}}
\end{aligned}$$
- $n_i$ - sample size
- Each treatment may have different sample size $n_I$.


- *e.g.* take a sample of patients on the *high dosage* treatment. So $Y_{i_j} =$ the $j$th observation for the $i$the treatment
- *e.g.* $Y_{i_j}$ could be the blood pressure of $j$th patient on the high dose treatment

##### First Simplified Case (Balanced Case)
- All treatments have the same sample size (balanced) $n_i = n$ for all treatments $i$
- To simplify further we assume a ***statistical linear model***
$$\begin{aligned}
    Y_{i_j} &= \mu + \tau_i + \epsilon_{i_j}
\end{aligned}$$
- $\mu$ - some fixed mean
- $\tau_j$ - some parameter
- $\epsilon_{i_j}$ some noise random variable.
- $1 \le i \le a, 1 \le j \le n$
- $\mu + \tau_i$ - renamed to $\mu_i$
- $\mu$ is a common mean across all treatments
- $\tau_i$ - ***treatment effect*** some parameter associated to the $i$th treatment.
- $\epsilon_{i_j}$ is a random variable *noise*/*error*

As usual, assume the $\epsilon_{i_j}$ are standard normal and *iid* with variance $\sigma^2 (\epsilon_{i_j} \sim N(0, \sigma^2))$
- Then $Y_i \sim N(\mu + \tau_i, \sigma^2)$

> ***Remark***
> If $\mu_i = \mu + \tau_i$ then $\mu_i$ is the $i$th treatment mean.
> $$\begin{aligned}
>     Y_{i_j} \sim N(\mu_i, \sigma^2)
> \end{aligned}$$

**Fourth simplifying assumption***: we assume that the experimenter is specified choosing the treatments to determine something/test the treatment effects ($\tau_i$)/equiv the treatment means ($\mu_i$). (fixed-effects model)

# Develop Anova for a fixed-effects model
- Assume $\sum_{i=1}^a \tau_i = 0$
- We want to test the hypothesis
$$\begin{aligned}
    \mu_1 = \mu_2 = \dots = \mu_n
\end{aligned}$$
- This is equivalent (by the assumption that $\epsilon_{\tau_i} = 0$) that
$$\begin{aligned}
    \tau_1 = \tau_2 = \dots = \tau_n = 0
\end{aligned}$$

*So* if
$$\begin{aligned}
    H_0&: \tau_1 = \tau_2 = \dots = \tau_a = 0 \\
    H_a&: \tau_i \ne 0 \text{ for some } i
\end{aligned}$$
