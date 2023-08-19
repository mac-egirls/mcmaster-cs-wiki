---
title: 30 - Confidence Intervals for Proportion.md
description:
published: false
date: 2023-07-02 19:22:47.755690
tags:
editor: markdown
dateCreated: 2023-07-02 19:22:47.755691
---

2022-11-11

- Suppose we take some population and we are interested in a certain subset.
    - *population*: all people, *subset*: people who prefer pepsi over coke.
- Let $p$ be the true proportion of the population in the subset.
    - maybe $p = 0.6$ of people prefer pepsi
- Let's assume we take a *large* sample of the population (say $n \ge 30$)
- Out of that sample, let $X = \#$ of samples that are in the subset
    - how is $X$ distributed?
    - $X \sim Bin(n, P)$ ($p$ is unknown)
- Let $\hat P = \frac{X}{n}$
- $E[\hat P] = \frac{E[X]}{n} = \frac{np}{n} = p$
- For $n$ large enough,
$$\begin{gather*}
    X - \frac{np}{\sqrt{np(1-p)}} \approx N(0, 1)
    \\\equiv \\
    \frac{\hat P - p}{\sqrt{\frac{p(1-p)}{n}}} \approx Z \sim N(0, 1)
\end{gather*}$$

Let's try to build a $100(1 - \alpha)\%$ CI for $p:$
- $z_{\frac{\alpha}{2}}$ the value s.t. $P\left(Z \le z_{\frac{\alpha}{2}}\right)= 1 - \frac{\alpha}{2}$
$$\begin{aligned}
    1 - \alpha &\approx P\left(-z_{\frac{\alpha}{2}} \le \frac{\hat P - p}{\sqrt{\frac{p(1-p)}{n}}} \le z_{\frac{\alpha}{2}}\right) \\
    &= P\left(\hat P - z_{\frac{\alpha}{2}} \sqrt{\frac{p(1-p)}{n}} \le p \le \hat P + z_{\frac{\alpha}{2}} \sqrt{\frac{p(1-p)}{n}}\right)
\end{aligned}$$
- Not ideal because $p$ is unknown
- estimate with $\hat P$

> ***note***
> So a $100(1 - \alpha)\%$ CI on $p$ is
> $$\begin{aligned}
>     \hat P \pm z_{\frac{\alpha}{2}} \sqrt{\frac{\hat P(1-\hat P)}{n}}   
> \end{aligned}$$
> 
> ##### Remark
> The approx is good usually as long as $n \hat P > 5$, $n(1 - \hat P) > 5$

#### Example
Out of a random sample of 50 engineering students, 18 of them have had covid. Find a $99\%$ CI on the proportion of all engineering students who have had covid.

##### Solution
$\alpha = 0.01$ so $1 - \frac{\alpha}{2} = 0.995$.
- Table: $z_{\frac{\alpha}{2}} = 2.58$

What is $\hat P = \frac{18}{50} = 0.36$ so a $99\%$ CI is then
$$\begin{aligned}
    \hat P \pm z_{\frac{\alpha}{2}} \sqrt{\frac{\hat P(1 - \hat P)}{n}}
    &=
        0.36 \pm (2.58) \sqrt{\frac{(0.36)(1 - 0.36)}{50}}
    \\&=
        0.36 \pm 0.175
\end{aligned}$$