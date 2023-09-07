---
title: 15 - normal approximation in a binomial distribution.md
description: 
published: true
date: 2023-09-05T18:01:38.278Z
tags: 
editor: markdown
dateCreated: 2023-09-05T18:01:34.361Z
---

> ***Normal Approximation in a Binomial Distribution***
> Observe that the binomoial distribution $X \sim Bin(n, p)$ is roughly bell-shaped.
> 
> $$E[X] = np, Var(X) = np(1-p)$$
> 
> - If $n$ is really big (relative to $p$), then
> $$Bin(n, p) \approx N(np, np(1-p))$$
> 
> If you believe this, then if $X \sim Bin(n, p)$, then
> $$\begin{aligned}
> 	\frac{X -np}{\sqrt{np(1-p)}}
> \end{aligned}$$
> is approximately $\sim N(0, 1)$

![](/images/20221022011906.png)

## Remark
For technical reasons, it's often useful to include a "continuity correction."
$$\begin{aligned}
    P(X \le x)
    &= 
    	P(X \le x + 0.5)
    & & \text{\footnotesize(since $X$ is discrete)}\\&=
        P\left(z \le \frac{x+0.5-np}{\sqrt{np(1-p)}}\right)
\end{aligned}$$

**Similarly**
$$\begin{aligned}
    P(X \ge x) \approx  P\left(z \le \frac{x+0.5-np}{\sqrt{np(1-p)}}\right)
\end{aligned}$$

> ***What is big enough?***
> $n$ is big enough for a good estimate if
> $$\begin{aligned}
>     np > 5 && n(1-p)>5
> \end{aligned}$$

#### Example
Multiple choice test, 60 questions with 5 answers each. Guess randomly on each question, each outcome equally likely.
$X$ = \# of correct answers

Find $P(10 \le X \le 20)$?
- $p = \frac{1}{5}$
- $n = 60$
- $np = 12$, $n(1-p) = 48$, so it is big enough
- $X \sim Bin(60, \frac{1}{5})$
- $E[X] = 12$, $Var(X) = 60(\frac{1}{5})\left(\frac{4}{5}\right) \approx 9.6$

$$\begin{aligned}
    P(10 \le X \le 20)
    &\approx
        P\left(\frac{10-12}{\sqrt{9.6}} \le \frac{X-12}{\sqrt{9.6}} \le \frac{20-12}{\sqrt{9.6}}\right)
    \\&\approx
        P\left(\frac{10-12}{\sqrt{9.6}} \le \frac{X-12}{\sqrt{9.6}} \le \frac{20-12}{\sqrt{9.6}}\right)
    \\&\approx
        \Phi\left(\frac{20-12}{\sqrt{9.6}}\right) - \Phi\left(\frac{10-12}{\sqrt{9.6}}\right)
    \\&\approx
        0.788
\end{aligned}$$
- Should use continuity correction

