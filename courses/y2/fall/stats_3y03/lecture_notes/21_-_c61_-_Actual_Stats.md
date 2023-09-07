---
title: 21 - c6.1 - Actual Stats.md
description: 
published: true
date: 2023-09-05T18:08:21.248Z
tags: 
editor: markdown
dateCreated: 2023-07-03T00:28:04.023Z
---

Sample numerical data
$$\begin{aligned}
    \{x_1, \dots, x_n \} \subseteq \mathbb{R}
\end{aligned}$$
What kind of information can we extract from a sample.
- Measures of location/centrality
- measures of spread

# measure of location
> ***sample mean***
> Given a sample: $\{x_1, \dots, x_n\}$. The *sample mean* is
> $$\overline x = \frac{x_1 + \cdots + x_n}{n}$$

#### Example
$$\begin{aligned}
    \{2, 3, 4, 5\}, \overline x = 3.5
\end{aligned}$$


> ***sample median***
> The *sample median* is the "middle value" of hte data when the sample is arranged by magnitude
> - if the sample has even size, we take the median to be the mean of hte two middle values.

> ***mode***
> The value/values that appear most frequently

# Measures of Spread/Variation
Given a sample $\{x_1, \dots, x_n\}$.
> ***Sample Variance***
> $$\begin{aligned}
>     S^2 &= \frac{1}{n-1} \sum_{i=1}^n (x_i - \overline x)^2
> \end{aligned}$$
> *Recall*: If $X$ is a RV then $Var(X) = E[(X - E[X])^2]$.

Tedious to compute. But:
$$\begin{aligned}
    S^2
    &=
        \frac{1}{n-1} \sum_{i=1}^n (x_i-\overline x)^2
    \\&=
        \frac{1}{n-1} \sum_{i=1}^n (x_i^2 + \overline x^2 - 2 \overline x x_i)
    \\&=
        \frac{1}{n-1} \left(\sum_{i=1}^n x_i^2 + n \overline x^2 - 2 \overline x \frac{n}{n} \sum_{i=1}^n x_i\right)
    \\&=
        \frac{1}{n-1} \left(\sum_{i=1}^n x_i^2 + n \overline x^2 - 2 n \overline x^2\right)
    \\&=
        \frac{1}{n-1} \left(\sum_{i=1}^n x_i^2 - n \overline x^2\right)
\end{aligned}$$

> ***Population standard deviation***
> With population finite and consists of $N$ equally likely values.
> 
> ![](/images/20221122115349.png)

## Range
$$\begin{aligned}
    range(x_1, \dots, x_n) = max\{x_i\} - min\{x_i\}
\end{aligned}$$

Not great, because it's very sensitive to outliers.
$$\begin{aligned}
    \{1,2,3,1000000\} \leftarrow \text{stupid range}
\end{aligned}$$

*Better*: Interquartile Range. What are quartiles?

> ***Quartiles***
> - 1st quartile ($q_1$) is the value such that 25\% of the data is $\le q_1$.
> - 2nd quartile ($q_2$) is the value such that 50\% of the data is $\le q_2$. (this is the median!!).
> - 3rd quartile ($q_3$) is the value s.t. 75\% of the sample data is $\le q_3$.

> ***warning***
> Quartiles are not precisely defined, so it can vary between different pieces of software.

The IQR of the data is defined to be
$$\begin{aligned}
    IQR = q_3 - q_1
\end{aligned}$$

Remark: More generally, the $n^{th}$ percentile s the value such that $n\%$ of data is below it.

# Stem and Leaf Plots
Stem and leaf plots give away to visualize data sets that aren't too big.
Suppose we have a sample $\{x_1, \dots, x_n\}$ and each $x_i$ consists of two or more digits.

To construct a stemmed leaf plot follow the steps:
1. Split each $x_i$ into two parts
    - a *stem* consisting of 1 or more leading digits
    - a leaf, the remaining digits
2. Record the leaves next to the columns
3. Record the leaves next to the corresponding stem in ascending order
4. Write the units/label the median

#### Example
$$\begin{aligned}
    \{9.1, 9.2, 9.3, 10.4, 10.2, 9.1, 8.6, 8\}
\end{aligned}$$

| stem | leafs       |
| ---- | ----------- |
| 8    | 0, 6      |
| 8    | 1, 1, 2, 3 |
| 10   | 2, 4       |

# Frequency Distribution of Histograms
- Frequency diagrams and histograms give a nice, compact way to visualize data.
## Simple idea
- divide data into equally spaced bins
- Count the size of each bin and then plot it the counts.
- How many bins.
    - too many: lose the shape
    - too few: lose data
- As the sample gets large, $\# bins \to \infty$.
