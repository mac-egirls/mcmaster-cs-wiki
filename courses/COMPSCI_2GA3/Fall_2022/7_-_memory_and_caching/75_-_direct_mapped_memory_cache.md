---
title: 7.5 - direct mapped memory cache.md
description: 
published: true
date: 2023-07-04T04:10:44.135Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:41.381Z
---

# Cache Coherence Protocols
- When multiple processors are accessing and modifying the same value a cache coherence protocol is necessary
- All caches need to see write operations in the same order
- All caches need information immediately when value to be changed.
- In some cases a cache may need to be flushed - empty the cache
- Different strategies: common directory, snooping
    - ***common directory*** - somewhere there is a list of all the memory addresses and caches that called it. Whenever cache1 wants to change the value, it goes into a directory, notifies cache3 that the value has been changed
    - ***snooping*** - other way around from common directory. Goes from cache3 and monitors whether other caches are doing writes.

![](/images/20221125172230.png)

# Direct Mapped Memory Cache
![](/images/20221118110607.png)
==NOTE:== Addresses go higher, and groups of blocks have unique tag ids.

To get the offset of 0x14, we do
$$\begin{aligned}
    0x14 \mod 8
    &= 20 \mod 8 \\
    &= 4
\end{aligned}$$
![](/images/20221117160801.png)
The block id for 0x14 is
$$\begin{aligned}
    (0x14 \text{ div } 8) \mod 4
    &=
        00010 \mod 2^2
    \\&=
        10
\end{aligned}$$

![](/images/20221117161402.png)
![](/images/20221117161707.png)

# Hardware Implementation
![](/images/20221117162328.png)
- tags get brung down to the comparator

# Cache Size
- A 64-bit architecture (word = 8 bytes) has a DMMC with 128 lines, where each line is 16 words long

> ***How many bits is hte length of each tag?***
> $128$ lines $= 2^7$ blocks. so $7$ bits for block id.
> $16$ words $= 2^4$ bits. so $4$ bits for offset.
> tag id $= 64 - 7 - 4 = 53$ bits.

![](/images/20221118111849.png)
- add them together

# Self Associative Memory Cache
- Look through $K$ DMMCs in parallel
- Store multiple lines with same block ID / different tag ID
- Fully associative cache: each DMMC holds single line
- Allows implementing a LRU cache replacement policy





