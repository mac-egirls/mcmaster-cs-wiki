---
title: 5.2 - design patterns in assembly.md
description: 
published: true
date: 2023-07-04T04:10:15.204Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:12.804Z
---

# ARM Assembly
## Registers
![](/images/20221025011506.png)

## Frames and Stack
- When a function is called static memory is pre-allocated: the stack
- **Stack pointer *(SP)*** -  points to the top of the stack
- **Frame pointer *(FP)*** points to a sliding window on the stack corresponding to the current function
- **Intra procedural call *(IP)*** - is a temporary storage for the *FP*
- **Link register *(LR)*** - points to the return address when aa function gets called
- **Program counter *(PC)*** - points to the address of current instruction in memory
- **Control and Program Status Register *(CPSR)*** - holds flags related to the control flow of execution.
    - Set upon execution. Conditional branch checks the *CPSR* flags.
    - Most fields are 1 bit:
        - ***N***: Negative. Result is a negative number
        - ***Z***: Zero. Result is zero
        - ***C***: Carry. Result requires +1 bit to represent
        - ***V***: Overflow. Results in overflow

## Basic Instructions
![](/images/20221025012419.png)

## GDB Commands
```pascal
.data
var1: .word 3
var2: .word 4
.text
.global_start
_start:
    ldr r0, adr_var1 @ load memory address of var1
    ldr r1, =var2    @ load memory address of var2
    ldr r2, [r0]     @ load the value at memory address r0
    add r2, r2, #3   @ add 3 to r2, store in r2
    str r2, [r1]     @ store the value found in R2 to memory
    bkpl             @ breakpoint
adr_var1: .word var1 @ address to var1 stored here
```

```shell
# Compiling
as -g file.S -o file.o

# Linking
ld file.o -o file

# Running
gdb file
```
- `r` - runs the program
- `b` - sets a breakpoint
- `n` - step to next instruction
- `s` step into function
- `info registers` - prints out register contents
- `p $rX` - prints the contents of `rX`
- `x` - prints memory address, e.g., `x/i $pc`
- `q` - quits

#### Example: Hello World
![](/images/20221025014924.png)