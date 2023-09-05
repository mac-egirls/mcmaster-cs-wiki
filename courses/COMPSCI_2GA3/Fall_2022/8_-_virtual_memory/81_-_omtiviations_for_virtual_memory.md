---
title: 8.1 - omtiviations for virtual memory.md
description: 
published: true
date: 2023-07-04T04:10:47.652Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:45.172Z
---

# Virtual Memory Space
![](/images/20221118132446.png)
- Addresses between CPU and MMU are in a *virtual* address space (*may be* byte addresses and could not refer to a real location).
- MMU Talks to each physical memory in *physical* address space (word addressable memory).

# Motivations for Virtual Memory
- homogeneous integration of hardware
    - allows for integration of hardware in a homogenous way
    - *Example*, look at figure above
        - could have only 1 memory unit, and it's installed in the second controller interface
        - If using physical address space without virtual abstraction, will have hole in the MMU that was supposed to be taken up by the first controller interface.
        - Same situation 1 memory unit in first controller interface
- programming convenience
    - no ***absolute addresses*** (addresses with no regard for holes in memory like in the above example)
    - Want programs to run in their own isolated space
- support for multi-programming
    - multiple programs run at the same time 
- protection and encapsulation of programs and data.
    - not possible to access other memory

# Interleaved Memory Controllers
![](/images/20221118140125.png)
- Interleaving - virtual address $v$ maps to a physical address $p = v \text{ div } 4$ on memory bank $b = v \text{ mod } 4$. for a continuous memory space

![](/images/20221118140158.png)
- Virtual address $v$ on space $i$ maps to location $m = \frac{N \times i}{4} + v$. $v$ lives between $0$ to $M$.

- want a larger virtual space than a physical space.
    - can never squeeze a lot of data in physical memory if we have huge amounts of data
    - with virtual memory we can.

# Support for Multi-programming
- Multiple programs run simultaneously
    - We don't want to access the same memory
    - Both security and abstraction feature
- Early computers would either run single program or partition memory (allocate different parts of memory to different programs and it stays static like that)
    - highly inefficient
- *Solution*: MMU translates multiple virtual spaces to multiple physical spaces
    - multiple because there are different memory controllers
![](/images/20221118141524.png)
