---
title: 13 - continuous random variable.md
description:
published: false
date: 2023-07-03 00:49:52.996462
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.996463
---

2022-10-04
> ***Continuous Random Variable***
> $X$ is a CRV iff $range(X)$ contains an interval of real numbers.

#### Example
- Temp outside = $T$
- $S$ - the loudness of a sound
- $B$ - the volume of blood in a randomly selected human

#### Example

- Consider a circular dart board of radius 1, can't miss, and throw darks randomly
- Let $X =$ "The distance from the centre"
- $range(X) = [0, 1]$
- For $0 \le r < r' \le 1, P(r \le X \le r') = \dfrac{\pi r'^2 - \pi r^2}{\pi r^2} = \frac{r'^2}{r^2} - 1$
- *Notice*: as $r' \to r$, 
$$\begin{aligned}
    P(X = r) &= P(r \le X \le r)
    \\&= \lim_{r' \to r} P(r \le X \le r') = 0
\end{aligned}$$
- So $P\left(X = \frac{1}{2}\right)= 0$ even though we know it's "possible".

> ***Generally***
> If $X$ a CRV, then $P(X = a) = 0$. For any $a \in \mathbb R$.

> ***CRV PDF***
> Let $X$ a CRV. Then we say $f_X(x)$ is the *probability density function* (pdf) of $X$ iff
> 1. $f(x) \ge 0$ for all $x$
> 2. $\displaystyle \int_{-\infty}^\infty f_X(x)\ dx = 1$
> 3. $P(a \le X \le b) = \int_c^b f_X(x)\ dx$
> 
> #### Remark
> Since $P(X = a) = 0$, we have $P(a \le X \le b) = P(a \le X < b) = P(a < X \le b) = P(a < X < b)$
> 
> $$\begin{aligned}
> 	P(a \le X \le b) &= P(\{a \le X < b\} \cup \{X = b\}) & & \text{\footnotesize(mutiually exclusive)}\\
> 	&= P(a \le X < b) P(X = b)
> \end{aligned}$$

> ***Uniform Distribution***
> Let's say we have $X \in [a, b]$ with uniform probability in the interval. Then,
> $$f_X(x) = \begin{cases*}
> 	\frac{1}{b - a}, x \in [a, b] \\
> 	0, \text{otherwise}
> \end{cases*}$$


#### Example
Suppose $X =$ "the current in a copper wire", the current  ranges uniformly between 3.6 and 4.1 mA.

*Question:* $P(3.7<X<3.8) = ?$
$$f_X(x) = \begin{cases*}
	\frac{1}{4.1-3.6} = 2, x \in [3.6, 4.1] \\
	0, \text{otherwise}
\end{cases*}$$

$$\begin{aligned}
	P(3.7 \le X \le 3.8) &= \int_{3.7}^{3.8} 2\ dx \\
	&= 2(0.1) = 0.2
\end{aligned}$$

> ***FDA with CDF***
> Let $X$ be a CRV with pdf $f_X(x)$. How do we compute $P(X \le x) \leftarrow$ by definition, the cumulative distribution function.
> 
> $$\begin{aligned}
> 	P(X \le x) = F_X(x) = \int_{-\infty}^x f_X(t)\ dt
> \end{aligned}$$
> 
> By the fundamental theorem of calculus,
> $$\begin{aligned}
>     \frac{d}{dx} F_X(x) = f_X(x)
> \end{aligned}$$
> 
> #### Observation
> $$\begin{aligned}
> 	P(a \le X \le b) = F_X(b) - F_X(a)
> \end{aligned}$$
> 
> ### Properties of CDF's
> 1. $\lim\limits_{x \to \infty} F_X(x) = 1$
> 2. $\lim\limits_{x \to -\infty} F_X(x) = 0$

#### Example
$$\begin{aligned}
	F_X(x) &= \begin{cases*}
    	0, x \le -1 \\
    	\frac 1 2 (x+1)^2, -1 < x \ge 0 \\
    	1 - \frac{(x-1)^2}{2}, 0 < x < 1 \\
    	1, x \ge 1 \\
    \end{cases*}
\end{aligned}$$

$$\begin{aligned}
	P\left(X \le \frac{1}{2}\right) &= F\left(\frac{1}{2}\right)
	\\&= 1 - \frac 1 2 (\frac{1}{2}- 1)^2
	\\&= 1 - \frac 1 8 = \frac{7}{8}
\end{aligned}$$

What's the pdf?
$$\begin{aligned}
	f_X(x) &= \frac{d}{dx} F_X(x)
	\\&= \begin{cases*}
    	0, x \le -1 \\
    	x+1, -1 \le x < 0 \\
    	x-1, 0 < x \le 1 \\
    	0, x \ge 1 \\
    \end{cases*}
\end{aligned}$$

> ***E[X] and Var(X)***
> $X$ is a CRV, then
> $$\begin{aligned}
> 	E[X] &= \int_{-\infty}^\infty x f_X(x)\ dx
> \end{aligned}$$
> 
> If $h: \mathbb{R} \to \mathbb{R}$, then
> $$\begin{aligned}
> 	E[h(X)] = \int_{-\infty}^\infty h(x) f_X(x)\ dx
> \end{aligned}$$
> 
> - The *variance* of $X$ is
> $$\begin{aligned}
> 	\sigma_X^2 &= Var(X) 
> 	\\&= 
>     	E[(X - E[X])^2]
>     \\&=
>         \int_{-\infty}^\infty x^2 f(x)\ dx - \int_{-\infty}^\infty x f(x)\ dx
> 	\\&= E[X^2] - E[X]^2
> \end{aligned}$$
> - Sometimes easier than above

