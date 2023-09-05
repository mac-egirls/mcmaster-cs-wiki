---
title: 10.1 - two different IO paradigms.md
description: 
published: true
date: 2023-07-04T04:09:07.098Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:04.721Z
---

# How are IO Operations carried out?
- *Option 1*: each device exposed as an address
    - CPU performs fetch/store directly
    - Operations triggered and monitored by CPU
    - ***Programmed I/O***
- *Option 2*: Smart device carries out operations independently
    - Device must contain a processor
    - CPU sets high-level goals, local processor carries out operations and monitoring
    - Device is done, let's the CPU know what to do next. Called an ***interrupt***.
    - ***Interrupt-driven I/O***
![](/images/20221201102209.png)

# Programmed IO
- CPU takes control of all low-level operations on device
- Device can be very simple, fixed logic circuits

> ***Synchronization Issues***
> - CPU runs at a high clock rate than devices actually perform operations
> - Device operations order of magnitude slower
> - Result: CPU has to wait for device

> ***Programmed IO***
> CPU has to periodically check if operations complete through the use of ***polling***.

- Information Exchange via special registers on device
- CPU reads status registers and sets control registers
- Often CSR struct for convenience

