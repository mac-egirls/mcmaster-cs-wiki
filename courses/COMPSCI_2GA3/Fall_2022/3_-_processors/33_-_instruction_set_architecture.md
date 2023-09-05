---
title: 3.3 - instruction set architecture.md
description: 
published: true
date: 2023-07-04T04:09:47.001Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:44.442Z
---

- Stored program processors
- Sequence of instructions stored in memory
- Processor conceptually separate from program and function
- Allows for abstraction/modification

# The Fetch-Execute Cycle
```pascal
ip = start of program
Repeat forever
	instsruction = fetch (memory [ip])
	execute instruction
	ip++
```
- `ip` - the instruction pointer
	- moves through the program in memory and performs each step

# Program Translation
![](/images/20220928104251.png)
==NOTE:== Steps used to translate a source program to a binary code representation used by a processor

1. **Preprocessor** - expands macros, makes a modified source program
2. **Compiler** - translates the program into assembly language.
3. **Assembler** - translates the assembly language into a relocatable object program with a combination of binary code and references to external library functions.
4. **Linker** - Processes the relocatable object program by replacing external function references with the code for the functions. Does so by searching libraries for the name.

# Instruction Set Architecture (ISA)
- The design of all available instructions for a processor is known as the Instruction Set Architecture
- Defines
	- What instructions are available
	- What each instruction does. Pre/post conditions
	- Number of operands, operand encoding, instruction encoding, result
- Three most-common ISA families today: x86, arm and RISC-V.

# Assembly Language
- Low level programming language
- Intermediate step to machine instructions
- Direct mapping to instructions
- Human readable, some shortcuts, macros

# Typical Instruction Format
- **Opcode** - the operation to be performed. A number. Operations all have a unique opcode. 
- **Operands** - a value to perform an operation on. Like a *function argument*. Instruction set definitions specific the exact number of operands and their values.
- **Results** - operands specify where the processor should place results.
- Most processors have a field containing the opcode and the operands.
![](/images/20220929222400.png)

- Different types of instructions:
	- Arithmetic Logic Unit (ALU) operations
	- Register access
	- Memory access
	- Program flow control

# Branching
- Moving the instruction pointer to a different location in a program
- Necessary for *conditions, loops*, etc.

```pascal
!p = start of program
repeat forever
	Instruction = fetch (memory [ip])
	tmp = ip+1
	execute instruction
	ip = tmp
```

- The instruction may have executed a branching instruction, so we save our location for the next instruction in `tmp` so the instruction order is unchanged.

![](/images/20221009165741.png)
==NOTE:== some examples of branching instructions
