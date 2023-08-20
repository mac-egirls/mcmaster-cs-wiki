---
title: 1 - digital logic.md
description: 
published: true
date: 2023-08-19T23:27:33.533Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:21.943Z
---

[]()# Digital Logic
## Ohm's Law
$$V = IR$$

## Ohms Over a Parallel Circuit
$$\sum_{k=0}^n \frac 1 {R_k}$$

## Transistors
![](/images/20220908105412.png)
- G - Gate/doped silicon. 
	- Doped silicon means there's an injection of a positively charged metal in the silicon
- D - Drain
- S - Source (current)
- B - Base

### Abstract Diagram
![](/images/20220908105528.png)
- (**left**) - transistor is by default closed
- (**right**) - transistor is by default open
- PNP - +/-/+
- NPN - -/+/-
- In some circuits, the low and high are a set voltage

#### Boolean Not
![](/images/20220908110054.png)

- 0 volts acts as grounding. There may be some voltage even when the high voltage is disconnected, so we ground the wire as well.

| input | output |
| - | - |
| 0 | 1 |
| 1 | 0 |

#### NAND
![](/images/20220908111012.png)

| A | B | O |
| - | - | - |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

#### XOR
![](/images/20220912152440.png)

| A | B | O |
| - | - | - |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

##### Case A=0, B=0
![](/images/20220912155709.png)

Thus Output is 0.

##### Case A=0, B=1
![](/images/20220912155724.png)

Thus Output is 1

##### Case A=1, B=0
![](/images/20220912155757.png)
Thus Output is 1

##### Case A=1, B=1
![](/images/20220912155807.png)
Thus Output is 0

### Logic Circuits
![](/images/20220912104823.png)
- inverter - not gate
- nor - or gate followed by inverter

#### Example: Logic Circuits
![](/images/20220912105651.png)

> ***Corresponds to logic formula***
> $$NOT(NAND(X, NOR(Z, NOT(Y))))$$

### Adding Binary Numbers
#### Half Adder
![](/images/20220912111117.png)
- basically XOR but also contains the AND gate for the carry

#### Full Adder
![](/images/20220912111315.png)
![](/images/20220912111347.png)
![](/images/20220912111447.png)
- $c_0$ - carry from $a_0 + b_0$
- $c_{01}$ - carry from $c_{in} + (a_0 \oplus b_0)$

| $a_0$ | $b_0$ | $c_{in}$ | $c_{0}$ | $c_{01}$ | $c_{out}$ |
|-|-|-|-|-|-|
| 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 |
| 1 | 1 | 0 | 1 | 0 | 1 |
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 1 | 1 |
| 1 | 0 | 1 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 | 1 |

- The table shows that $c_0, c_{01}$ never overlap, so we can safely OR them to get the final $c_{out}$.

#### n-bit adder
![](/images/20220914104328.png)

### Arithmetic Logic Unit (ALU)
![](/images/20220914162459.png)
- ALU box in schemes
- Implements hardware for addition, subtraction, logic operations
- Control path and data path
	- lines between in and out of ALU is called the data path

### Implementing Memory
- Fixed logic circuits
- Maintain state
- Load operands
- Store results
- From theory: a Turing machine needs tape

### SR Latch (NOR)
![](/images/20220914171628.png)
- R - Reset
- S - Set
- In digital electronics, reset means output must be 0, and set means output must be 1.
- The basic storage element. Like the name suggests it latches 0 or 1.
- When $R$ and $S$ inputs are switched, $Q$ and $\overline Q$ could remain. That is because:
	- Computation in circuits do not happen instantly
	- Each gate opens sequentially: A -> B -> C -> O
	- Takes like 1 pico second to propagate through each gate


> ***Truth table for NOR gate***
> 
> |A|B|Y|
> |-|-|-|
> |0|0|1|
> |0|1|0|
> |1|0|0|
> |1|1|0|

#### Case 1: $S = 0, R = 1$
![](/images/20220914172535.png)
As shown in the truth table, if any value $S, R$ is set, then output will be 0. Thus $Q$ is 0, which also relates to how $R$ is for reset.

This is a storage device, so when the input is removed, $Q$ and $\overline Q$ must remain 0 and 1. And they do!

When $R = 0, S = 0$, for a pico second, $\overline Q$ is still 1, so it provides 1 as input to the top NOR gate, which makes $Q$ 0, so the bottom NOR gate will still output 1 for $\overline Q$.

This stored condition is called memory.

#### Case 2: $S = 1, R = 0$
Works the same way but opposite in **Case 1**.

#### Case 3: $S = 1, R = 1$
![](/images/20220914173751.png)
CONTRADICTION since $Q \ne \overline Q$ but we have $Q = \overline Q$. So $S = 1, R = 1$ are not used.

#### Case 4: $S = 0, R = 0$
The thing you will see now will disturb you. Start the analysis with $Q$.
![](/images/20220914174120.png)
- Does not store the previous output

Start the analysis with $\overline Q$.
![](/images/20220914174228.png)
Now we have different outputs for the same configuration of $R$ and $S$.

> *****Cases 3 and 4** are bad***
> We don't use **Cases 3 and 4**.

> ***Summary***
>
> S|R|$Q$|$\overline Q$
> -|-|-|-
> 0|0|memory (as before)
> 0|1|0|1
> 1|0|1|0
> 1|1|***no***

### SR Latch (NAND)
![](/images/20220915103158.png)
> ***Summary***
> 
> S|R|$Q$|$\overline Q$
> -|-|-|-
> 0|0|***not used***
> 0|1|1|0
> 1|0|0|1
> 1|1|memory

### Latch
![](/images/20220914105855.png)
- Control - decides whether we store input or not

|D|E|A|B|C|O|
|-|-|-|-|-|-|
|`*`-|0|1|1|$\lnot$O|O|
|D|1|$\lnot$D|D|$\lnot$D|`**`D|
- `*` If $E = 0$, it does not matter what value $D$ is because NAND gates will always be 1 if at least one input is 0. The output remains the same.
- `**` If O is 0 or 1, the output will end up being D.
- you can see that $A$ and $B$ will never be the same so **Case 3 and 4** will never occur.

## Registers
![](/images/20220914180000.png)
Basically when we set enable, we write the value to the register. Otherwise, values in the register remain the same.

## Propagation Delays
- Typical propagation takes ~ 100 ps

## The need to synchronize
- Clock - "driver" of a logic circuit
	- What drives computation in a set of logic circuits
- oscillator
- Clock frequency $f = \frac 1 T$
	- measured in Hz
- Complex Circuits - multiple clocks

### Binary Counter
![](/images/20220915233352.png)
- Output starts at 0, but counts up every time the input transitions from 0 to 1.

### Decoder/DeMultiplexor/Demux
![](/images/20220915234334.png)
- $b_0, b_3$ - n-bit inputs
- Selects one of $2^n$ outputs
- single integrated circuit that uses a binary value to map an input to a set of outputs.
- Only one output of a decoder is on at any time; all others are off
- Part of a circuit to handle the task of performing many steps in sequence
- Basically the binary number the inputs make will translate to which number of the outputs it will be.


> ***Circuits in use***
> ![](/images/20220915234745.png)

### Multiplexer / DeMultiplexer
![](/images/20220915104851.png)
![](/images/20220915104929.png)
- $a, b$ are control lines

## Fixed vs Programmable Logic
Types of logic circuits;
- Fixed logic circuits - pre-determined function
- programmable logic
	- Example: field programmable gate array (FPGA)
- Stored program and re-programmable circuits

## Hardware Design Principles
- Replication vs Iteration
- Gate minimization
- Power
- Abstraction

