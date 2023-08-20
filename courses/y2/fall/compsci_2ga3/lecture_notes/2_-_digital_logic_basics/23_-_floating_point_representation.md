---
title: 2.3 - floating point representation.md
description: 
published: true
date: 2023-07-04T04:09:36.346Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:33.330Z
---

# Binary Fractions
- How do we represent a fractional number?[]()
$$3.5_{10} = \frac{35_{10}}{10_{10}} = \frac{7_{10}}{2_{10}} = \frac{111_2}{10_2} = 11.1_2$$

> ***Convert Binary Floating Point to Decimal***
>  1. Say we have a binary number $b.f_0f_1f_2f_3\dots$, with $f_0, \dots$ the floating digits.
>2. Multiply by 2, and remove $b$: $f_0.f_1f_2f_3\dots$
>3. If $f_0$ is 1, then that digit in the result is set. In decimal, it will still be 1 since $1_2$ in decimal is still 1.

#### Example: Convert $0.5625$ into binary
$$\begin{aligned}
	0.5625 \cdot 2 &= 1.125 \\
	0.125 \cdot 2 &= 0.25 \\
	0.25 \cdot 2 &= 0.5 \\
	0.5 \cdot 2 &= 1
\end{aligned}$$
Thus the binary representation is $0.1001$

# IEEE 754 Floats
![](/images/20220921110115.png)

```cpp
0 01010110 11000001111100110101111

0 00000000 00000000000010101101100
0 00000000 00000000000000000001111 &
------------------------------------
                              1100

1 01010110 11000001111100110101111
0 00000000 00000000000000101010110
0 00000000 00000000000000011111111
0 00000000 00000000000000000000110

0 000 0110
```

> ***Binary Scientific Notation***
> $$1.m_2 \cdot 2_{10}^{e-b}$$
> - $m$ - mantissa is normalized (the most significant bit is always a 1)
> 	- The first bit is always implicit
> - $e-b$ - exponent
> 	- $e$ - exponent in memory
> 	- $b$ - bias. Half the exponent in memory's range
> 	- If the *exponent in memory* takes up 5 bits, then the bias will be $2^{5-1}-1$

# Special Numbers
|Special value | exponent|mantissa|
|-|-|-|
|zero|0|0|
|$\pm \infty$|all 1s|0|
|NaN|all 1s|$\ne 0$|

#### Example
![](/images/20220921111918.png)

# Binary Coded Decimal
- Some decimal numbers are infinite binary fractions
$$0.1_{10} = 0.0(0011)_2$$
- inevitable rounding errors
- Alternative: encode every decimal digit in 4 bits (since 9's representation is $1001$ which needs 4 bits.

|Digit Endcoding|0; 0x0|1; 0x1|2; 0x2|3; 0x3|4; 0x4|
|-|-|-|-|-|-|
|Digit Encoding|5; 0x5|6; 0x6|7; 0x7|8; 0x8|9; 0x9|

# Representing Characters
- ASCII - American Standard Code for Information Interchange
- One byte characters
- What about non-standard characters?
- Unicode UTF-8 set: variable length encoding
- 21-bit encoding in up to 4-byte field
	- 11 bits are reserved for some weird leading bit shit

![](/images/20220922110602.png)

> ***Example***
> ![](/images/20220922110727.png)

# Compound Data Types

> ***example***
>   ```c
> struct example {
>	int16_t n;
>	float nmb;
>	int q;
>};
>```
>

- Data packed by compiler (everything is contiguous in memory)
- not a great idea
- Has something to do with assignment

