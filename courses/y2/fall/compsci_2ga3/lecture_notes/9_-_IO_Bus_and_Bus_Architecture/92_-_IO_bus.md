---
title: 9.2 - IO bus.md
description: 
published: true
date: 2023-07-04T04:11:02.677Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:11:00.378Z
---

# Bus Architecture
> ***Definition***
> A bus is a digital communication mechanism that allows two or more devices to exchange data.

![](/images/20221124110424.png)
- Different designs (open, proprietary)
- Different applications
- Different interface controllers
- Interface controller implements bus access protocol

# Physical Ipmlementation
![](/images/20221124110825.png)

# Control Address and Data Lines
![](/images/20221124111229.png)
- Different lines dedicated to different functions
- ***Control lines***: take control of bus, request transfers, set signals interrupts
- ***Address lines***: transmit the address in a fetch/store operation
- ***Data lines***: transmit data.

# Data/Address Multiplexing
![](/images/20221124111621.png)
- When data wider than interface width $\to$ data multiplexing
- More optimization possible: joint data/address multiplexing
- Key idea: use address lines and data lines together
- implement protocol, transfer address and data sequentially over shared lines


