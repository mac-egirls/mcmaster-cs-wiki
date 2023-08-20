---
title: 10.5 - direct memory access.md
description: 
published: true
date: 2023-07-04T04:09:17.337Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:14.991Z
---

# Direct Memory Access (DMA)
- Context switching is expensive, can we minimize \# of interrupts?
- Key idea; let smart device to fetch/store from memory directly
    - Improves performance by allowing a device to transfer data between the device and memory without using the processor.
- only trigger interrupt when buffer is full

# Buffer Chaining
- Possible to chain buffers and operations for better performance
- processors allocates multiple buffers, creating a linked list in memory
- IO device gets passed the list, allowing it to fill each buffer
- Smart devices can use the bus to read values from memory, so it can follow the linked list and place incoming packets in successive buffers

![](/images/20221201212803.png)

#### Example: high-speed network
- packets arrive in *bursts*; set of packets arrives back-to-back with minimum time between successive packets.
- If network interface uses DMA, device interrupts the processor and then processor must 
    - place the packet in memory
    - specify the next packet's buffer location and restart the device.
    - Must happen before next packet arrives
- Other devices may also be generating interrupts, so processor gets delayed
- linked buffers means device can follow the linked list and place incoming packets in successive buffers
