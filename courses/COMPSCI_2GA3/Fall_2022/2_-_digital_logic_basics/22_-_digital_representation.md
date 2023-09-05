---
title: 2.2 - digital representation.md
description: 
published: true
date: 2023-07-04T04:09:32.303Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:29.712Z
---

# Unsigned Integers
- Byte interpreted as unsigned binary integer
- Binary Weighted Positional Representation
$$b = \sum_{i=0}^k b_i 2^i$$
- How many integers in a $k$-bit byte?
- Maximum value: $2^k-1$

# Binary and hexadecimal
- Hexadecimal for better binary representation
- Binary is commonly grouped into 4 bits, so one digit in hexadecimal is conveniently one group of binary
- 1 byte = 2 hex digits

# Signed Integers
- sign-magnitude
	- $s|m$
	- If the sign bit is "0", the number is positive. If it is "1", the number is negative.
	- ![](/images/20220919105758.png)
	- Gives 2 ways to represent 0
- one's complement
	- if $s = +$, then $m$ else $\lnot m$
	- Takes the complement of every bit
|positive|decimal|one's complement|decimal|
|-|-|-|-|
|000|0|111|0|
|001|1|110|-1|
|010|2|101|-2|
- still has 2 ways to represent 0

- two's complement
	- If $s = +$, then $m$ else $\lnot (m-1)$

![](/images/20220919110735.png)

- subtracting $a-b$ is basically taking the two's complement of $b$ and adding: $a + (-b)$

# Casting and Filling Integers
Given 8-bit integer $-0x5$, convert to 16 bit:
- Sign magnitude:
	- $1|0000101$ -> $s|0\dots 0m$
- One's complement
	- $1|1111010$ -> $s|s \cdots s|7 LSB$
- Two's Complement
	- Same with one's complement