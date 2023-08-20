---
title: 10.3 - interrupt-driven IO.md
description: 
published: true
date: 2023-07-04T04:09:10.504Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:08.128Z
---

> ***Paradigm Shift***
> Instead of synchronous programming (Device and CPU are synchronized), allow device to work asynchronous and interrupt processor when done.

Require special design:
- *I/O device hardware*: on-board processor and ability to raise interrupt
- *I/O bus architecture*: support for interrupt signals
- *processor architecture*: context switching
    - change which program is being run
    - How multi-programming/multi-threading is being run
- *programming paradigm*: OS needs to support interrupts

# Interrupt Vectors
- Every time a device triggers an interrupt signal, OS needs to respond
- How do we know appropriate response to interrupt by device *d*?
- We  call function handler `i[d]`
- We Pointer to function is known as an interrupt vector
![](/images/20221201111134.png)

# Fetch-Execute with Interrupts
![](/images/20221201111528.png)
- If interrupted, CPU branches to interrupt handler
- Once interrupt is handled, clear signals and restore state
- What if interrupt handler is interrupted?

# Interrupts: OS view
- At boot time OS fills table with interrupt handlers per device
- Device IDs can be decided either by plug-in slot, or set by BIOS
- Hot-plug devices, e.g. USB: new device plug-in triggers interrupt, handler allocates device id and interrupt handler for new device
- Handling devices usually through *device drivers*
