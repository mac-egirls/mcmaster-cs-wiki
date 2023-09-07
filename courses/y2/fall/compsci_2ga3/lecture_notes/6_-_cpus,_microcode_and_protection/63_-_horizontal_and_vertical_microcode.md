---
title: 6.3 - horizontal and vertical microcode.md
description: 
published: true
date: 2023-07-04T04:10:25.651Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:23.290Z
---

# Vertical Microcode
- Sequential coding
    - Takes a macro instruction. Declares it as if it were implemented in microcode
- One centralized unit sequentially instructing new things
    - Control one functional unit at a time
    - microcontroller centralizes workflow
- Needs fast microcontroller
- Intuitive to code macro instructions

#### Example: 32-bit addition with 64-bit microcontroller
- One 32-bit register is split in half to be made from two 16-bit registers (R1_low, R2_high)

```armasm
add32 R0 R1 R2:
    mov r2 R1_low    ; r2 = R1_low
    mov r3 R2_low    ; r3 = R2_low
    add r1 r2 r3     ; r1 = r2+r3, ofw is carry bit
    mov r5 ofw       ; r5 = ofw
    mov r2 R1_high   ; r2 = R1_low
    mov r3 R2_high   ; r3 = R2_low
    add r0 r2 r3     ; r0 = r2+r3, ofw is carry bit
    add r0 r5 r0     ; r0 = r5+r0
    mov R0 r0,r1     ; R0_low = r1, R0_high = r0
    set ofw          ; 
```

# Horizontal Microcode 
- Control multiple functional units simultaneously
- Each instruction executes several operations in parallel
- They are not all the same type of processor
![](/images/20221102122139.png)
- ALU takes 2 [operands](/courses/y2/fall/compsci_2ga3/lecture_notes/6_-_cpus,_microcode_and_protection/6.3_-_horizontal_and_vertical_microcode.md)
    - operands like local storage for the [arithmetic logic unit](/courses/y2/fall/compsci_2ga3/lecture_notes/6_-_cpus,_microcode_and_protection/6.3_-_horizontal_and_vertical_microcode.md)
- Data transfer mechanism - the "bus". Units can put or fetch data from it.
![](/images/20221102122846.png)
- `noop` - don't do anything
- operand
    - 1 - fetch from BUS/receive data

![](/images/20221102135306.png)
- move data r4 to operand1
    - command: 000 - noop
    - operand1: 1 - receive data
    - operand2: 0 - noop
    - result1,2: 0 - noop
    - Unit: 01 0100 - fetch from register 4 

#### Example: 32-bit addition with 64-bit microcontroller
- Macro instruction: `add R0, R1, R2`
- Assume
    - `R0 -> r0, r1`
    - `R1 -> r2, r3`
    - `R2 -> r4, r5`
- Assume little endian, so `R0_low = r0` and `R0_high = r1`
- `r15 -> overflow`

![](/images/20221102142401.png)

# Multi-Cycle and Parallel Operations
- In some cases operations take multiple cycles
- So we instruct the ALU to continue previous operation for second cycle in a row:
![](/images/20221102143451.png)
- 111 - continue
- Some cases, next operation is already performed simultaneously by using independent units.
- parallelism is possible when a resource is not blocked

# Lookahead Execution
- Microcontroller can look ahead to next instruction and perform optimization
- Need to preserve computation semantics
- Lookahead for conditional branching: branch prediction or parallel branch, execution, depending on hardware.


