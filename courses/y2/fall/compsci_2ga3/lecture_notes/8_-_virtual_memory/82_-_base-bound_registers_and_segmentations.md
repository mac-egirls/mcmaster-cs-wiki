---
title: 8.2 - base-bound registers and segmentations.md
description: 
published: true
date: 2023-07-04T04:10:51.682Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:48.780Z
---

# Base bound registers
- MMU keeps track of mapping between virtual space and a pair (base, bound)
- *Base* points to memory address that maps to virtual address 0
- *bound* can be scaled dynamically and points to end of memory space
![](/images/20221118141905.png)

> ***Problems***
> - What if memory is full?
> - How do I decide where to place base?
> - what if virtual space is more than available memory space?

# Segmentation
- Instead of loading up memory space, split them into *variable size* chunks
![](/images/20221121103905.png)
- don't need to load up green space, so can split up memory
- In program counter, yellow sections are blocked by something else (like from another program)
![](/images/20221121104208.png)
- load up memory in available memory space
![](/images/20221121104234.png)
- if no more memory, we replace previously used memory with virtual memory
- **Can have $M>N$ in this case**

> ***Key Ideas and Issues***
> **Ideas**
> - Split up program meory space into *variable size* chunks
> - Exploits fact that most program memory is idle
> - When segment needed, it's loaded on demand
> - potentially replace old segment
> 
> **Issues**
> - How to chooes optimal segment splits?
> - How to avoid memory fragmentation?

# Demand Paging
> ***Key Idea***
> Split up program memory space into *fixed size* chunks called ***pages***.
- easier implementation
- Requires cooperation between software and hardware

| software                              | hardware                                |
| ------------------------------------- | --------------------------------------- |
| configure hardware                    | handle address mapping                  |
| monitor page use                      | record when a page is used              |
| move pages between memory and storage | detect access attempt to a missing page |

> ***Terminology***
> - ***page*** - a fixed-size block of a program's memory space
> - ***frame*** - a corresponding slot in physical memory of the same fixed size
> - ***load*** - move contents of a page from hard drive into a frame in memory
> - ***swap*** - exchange a resident page for naother page from storage
> - ***resident page*** - a page currently in memory
> - ***page table*** - an array that holds pointers mapping from page number to physical address of the frame where page resides.
> - ***replacement policy*** - a decision policy for choosing what page to swap

# Page Table
- ***page table*** is an array of pointers to addresses of pages/frames
- Allocated for all pages in a program's memory space
- Each entry also maintains several flags:
    - presence bit: set if page is resident (NULL if not loaded)
    - use bit: set every time an address on the page has been fetched, re-set if page not used for a fixed number of cycles
        - useful because we might want to replace a page
        - Least used page will be swapped out if we want to add a new page
    - modified bit: set if a memory address on the page has been written to.

![](/images/20221121105824.png)

## Address Translation
![](/images/20221121110624.png)
- $O$ - offset
- Want to access address $a$. Each page is $P$ bytes long.
    - $P = 2^x$ since we want bit shifts
    - $x$ - number of offset bits
- Page number $N = a \text{ div } P$
    - Since $P$ is a power of 2, can bit shift.
- Fetch the frame address $F = P_t[N]$
- Calculate the offset $O = a \mod P$
- Thus physical address of $a$ is $F+O$

#### Example
Assume virtual byte addressing, 32-bit architecture with 4096 pages, each 32KB ($2^{10}$ bytes long) long. Look up $a = 0x0035924E$
- 4096 pages = $2^{12}$ pages
- $32$ KB $= 32 \times 2^{10} = 2^{15}$ bytes
- Offset $= a \mod 2^{15}$. The last two bytes of $a = 0x924E = 100100100100110$. So $O = 001001001001110 = 0x124E$
- Frame $= P_t[N]$ and $N = 001101011 = 0x06B = 107$. Let's say that address returns $F = 0x00118000$
- Then $a_{phys} = 0x0011924E$



