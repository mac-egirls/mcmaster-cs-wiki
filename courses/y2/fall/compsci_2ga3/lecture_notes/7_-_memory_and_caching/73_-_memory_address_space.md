---
title: 7.3 - memory address space.md
description: 
published: true
date: 2023-07-04T04:10:36.209Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:33.663Z
---

- How much physical memory can we have in an architecture?
    - size of address
    - address is word-size

- If using byte address we have a factor of `N` less memory (`N` is word size)

| Bits             | Bytes                     |
| ---------------- | ------------------------- |
|                  | 1 byte = $2^3$ bits           |
| 1 KBit = $10^3$ bits | 1 Kb = $2^{10}$ bytes = $2^{13}$ bits |
| 1 MBit = $10^6$ bits | 1 Mb = $2^{20}$ bytes           |
| 1 GBit = $10^9$ bits | 1 Gb = $2^{30}$ bytes           |

#### Example
64-bit word size, Can represent $2^{64}$ word addresses, or $8 \cdot 2^{64} = 2^{67}$ bytes. This is $2^7 \cdot 2^{60}$ or 168 exabytes. With byte addressing it is $16 \cdot 2^{60}$ or $16$ exabytes.

# Memory Management Unit
![](/images/20221110111737.png)

- Multiple physical memory chips can connect to one common interface: the memory management unit (MMU)
    - talks to memory installed in memory card slots
- Provides common address space to processor
    - could be virtual addresses in the *interface*
- Implements virtual memory, caching

# Common Address Space
![](/images/20221110112148.png)
- How to combine address spaces?
- Four memory chips, each has address `0` to `N`
- MMU provides addresses `0` to `4N`
- Sequential and interleaved mode


