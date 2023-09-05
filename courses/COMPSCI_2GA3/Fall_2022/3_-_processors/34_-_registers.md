---
title: 3.4 - registers.md
description: 
published: true
date: 2023-07-04T04:09:50.710Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:48.228Z
---

# Registers
![](/images/20220930000419.png)
- Many latches
- Similar to memory; Fetch/store semantics
- Types
	- General-purpose
	- Floating point
	- Instruction pointer
	- Comparison operation

## Workflow with registers
- Load data from memory to register
- Perform ALU operation
- Store result from register to memory/load data from memory back to register
- Volatile memory. Data from it might be changed after branching to another function

## Register Banks
![](/images/20220930000735.png)
==Note:== Illustration of eight registers divided into two banks. Hardware allows the processor to access both banks at the same time.
1. Allows parallel access within same clock cycle -> efficiency
2. Some operations require operands from banks
3. Register bank conflicts

#### Example: Register bank Conflict
```haskell
R <- X + Y
S <- Z - X
T <- Y + Z
```
- By *2.*, operands must come from different banks. So,
- Assume $X$ and $Y$ are in corresponding register banks $A$ and $B$.
- $Z$ must then be in the opposite bank from $X$, so $B$.
- $Y+Z$ cannot happen since $Y, Z \in B$, so there are no possible assignments for $X, Y, Z$.
- A *register conflict* occurs.

##### Solution
Must reassign registers, moving registers, or insert an instruction to copy values to the opposite register.

# Subroutines and Register Windows

### Problem:
- Registers where we keep data, where we perform operations
- When we branch to a different function/program, it must also have access to the registers
- Naive way, we don't know which registers will be modified by this function.

### Solution
![](/images/20220930004555.png)
==Note:== a register window (a) before a subroutine call (b) during the call. Values $A, B, C,$ and $D$ are arguments.
- you have 16 registers in hardware, but software makes you only see 8
- the window moves when you call a function in order to pass arguments ($A, B, C, D$) or results
- Unshared registers are private for data protection.

- subroutines are like functions in `C`

