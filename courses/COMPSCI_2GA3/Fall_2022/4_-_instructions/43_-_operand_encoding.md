---
title: 4.3 - operand encoding.md
description: 
published: true
date: 2023-07-04T04:10:04.816Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:02.502Z
---

# Operands
- Arguments to instructions

## Representations
### Data Source
- An integer constant encoded into the instruction (*immediate value*)
- A number register that contains the data or reference to the data
- a memory address that contains the data or a reference to the data

### Data Destination
- In a numbered register
- in a specific memory location

# Fixed and Variable Number of Operands
- *Fixed* - bit fields always have same semantics
- *Variable* - use memory more efficiently

1. Zero operands - stack architecture; push/pop, implicit operands
```armasm
push ; r0 on the stack
load ; r0 = memory[r1]
add  ; stack contains r0+r1
```
2. One operand - implicit destination (accumulator)
```armasm
add rA ; acc = rA
add rB ; acc = rA+rB
pop rC ; rc = acc
```
3. two operands - specified destination, but only binary
```armasm
add rA, rB ; rA = rA+rB
```
4. three operands - specified destination, binary operations
```armasm
add rA, rB, rC ; rA = rB+rC
```

# Operand Encoding
## Implicit encoding
- opcode specifies the types of operands
- contains multiple opcodes for a given operation
![](/images/20221010235257.png)
==NOTE:== a separate opcode is used for each possible combination of operands
- some cases, an operand is always the same (operand to store the result is always the accumulator)

## Explicit encoding
- operand contains all information to interpret the operand
- operand field divided into two subfields: one specifies type, the other specifies value
![](/images/20221010235728.png)

