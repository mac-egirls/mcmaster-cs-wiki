---
title: 5.4 - assemblers.md
description: 
published: true
date: 2023-07-04T04:10:18.620Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:16.343Z
---

- Assembler translates assembly code to machine instructions
- Two-stage assembly procedure
    - Stage 0: (not counted) run pre-processor
    - Stage 1: assign address to every instruction and build label symbol table
    - Stage 2: translate instructions to binary. Substitute label with location from symbol table.

#### Example: Pseudo-Assembly
![](/images/20221027103354.png)

![](/images/20221027104323.png)
- Create a symbol table for the labels
- For instructions that take single operands, the bits in the place of the unused second operand could be set to all 0s or 1s.
