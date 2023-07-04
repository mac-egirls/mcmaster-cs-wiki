---
title: 5 - advanced sorts.md
description:
published: false
date: 2023-07-03 00:49:52.977061
tags:
editor: markdown
dateCreated: 2023-07-03 00:49:52.977070
---

![](/images/20221019001801.png)

> ***Recursion relations***
> - **Recurrence relation** - an equation that defines a sequence based on a rule that gives the next term as a function of the previous terms.
> - **recursion tree** - useful for visualizing what happens when such an equation is iterated, documenting not only the number of recursive calls, but also the amount of worek done at each step.
> 
> If our algorithm creates
> - *equal sub-arrays*, then every path of the recursion tree has the same height $h$
> - *unequal sub-arrays*, examine the longest path
>     - longest subarray takes longest to get sub-divided into one item
>     - so longest path follows the longest subarrays
>     - this path is the height of the tree
> 
> To determine the height of the longest path:
> $$\begin{aligned}
>     \frac{n}{k^h} = 1
> \end{aligned}$$
> - $k$ is the fraction by which $n$ is divied at each level to get the largest sub-array

![](/images/20221019002152.png)
==NOTE:== visualization of the division of multiple subarrays

#### Example
![](/images/20221019003041.png)





