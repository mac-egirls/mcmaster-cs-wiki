---
title: 31 - Confidence intervals continued.md
description: 
published: true
date: 2023-07-03T00:28:56.020Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:28:52.515Z
---

2022-11-15

- Suppose we are interested in a population and the proportion of that population in some subpopulation (proportion $p$ is unknown)
- We take a sample of size $n$.
    - Let $X=$ \# of samples in the subpopulation of interest
    - then $X = Bin(n, p)$
    - $\hat P = \frac{X}{n}$, then $\hat P$ an unbiased estimator for $p$
- a $100(1 - \alpha) \%$ CI for $p$ (assuming $n$ is large).
$$\begin{aligned}
    \left(\hat P - z_{\frac{\alpha}{2}} \sqrt{\frac{p(1-p)}{n}}, \hat P + z_{\frac{\alpha}{2}} \sqrt{\frac{p(1-p)}{n}}\right)
\end{aligned}$$
  Assuming $n \hat P \ge 5$ and $n(1 - \hat p) \ge 5$

#### Example
Out of 50 transistors, 18 are defective, find a $99\%$ CI for the proportion of defective transistors.
$$\begin{aligned}
    \hat p &= \frac{18}{50} = 0.36 \\
    \alpha &= 0.01 \Rightarrow 1 - \frac{\alpha}{2} = 0.995 \\
    z_{\frac{\alpha}{2}} &= 2.58
\end{aligned}$$

So a CI is
$$\begin{aligned}
    \hat P \pm z_{\frac{\alpha}{2}} \sqrt{\frac{\hat p(1 - \hat p)}{n}}
    &=
        0.36 \pm 258 \sqrt{\frac{0.36 \cdot (1 - 0.36)}{50}}
    \\&=
        0.36 \pm 0.175
    \\&=
        [0.185, 0.535]
\end{aligned}$$

# Error for population proportion
> ***error***
> The error term is
> $$\begin{aligned}
>     E &= z_{\frac{\alpha}{2}} \sqrt{\frac{\hat P(1 - \hat P)}{n}}
> \end{aligned}$$

We want a lower bound on the number of samples we need to guarantee a certain error.

## Rearrange

$$\begin{aligned}
    n \ge \left\lceil \left(\frac{z_{\frac{\alpha}{2}}}{E}\right)^2 \hat p(1 - \hat p) \right\rceil
\end{aligned}$$

How to proceed: *two ways*
1. If the sample size is large, $\hat p$ is a good estimate, so take
$$\begin{aligned}
    n \ge \left\lceil \left(\frac{z_{\frac{\alpha}{2}}}{E}\right)^2 \hat p(1 - \hat p) \right\rceil
\end{aligned}$$

2. Worst case analysis
    1. make $\hat P(1 - \hat P)$ as big as possible.
    2. $\hat P \in [0, 1]$
    3. $f(\hat P) = \hat P(1 - \hat P) = \hat P - \hat P^2$
    4. $f'(\hat p) = 1 - 2 \hat P$ - max at $\hat P = \frac{1}{2}$
    5. $= \frac{1}{4}$
So the worst case scenario is
$$\begin{aligned}
    n \ge \left\lceil \left(\frac{z_{\frac{\alpha}{2}}}{E}\right)^2 \frac{1}{4} \right\rceil
\end{aligned}$$
