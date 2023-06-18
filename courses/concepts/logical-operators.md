---
title: Logical Operators
description: operators used in Boolean algebra, and Propositional logic, and to represent logic gates
published: true
date: 2023-06-18T00:02:27.322Z
tags: logic, computer architecture
editor: markdown
dateCreated: 2023-06-17T12:35:58.416Z
---

# Logical Operators

A Logical operator takes in $n$ [truth values](/courses/concepts/boolean-algebra#truth-values), and returns a truth value. A logical operator can be defined using a [truth table](/courses/concepts/logic/truth-tables), or by combining other operators



## Operators


### $\lnot$ negation

code | english | logic gate | truth table
---|---|---
`!p` | not | NOT gate <br> ![not.png](/images/logic-gates/not.png) | <table><thead><tr><th>$p$ </th><th> $\neg p$</th></tr></thead><tbody><tr><td class="T">T</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="T">T</td></tr></tbody></table>


### $\lor$ disjunction

code | english | logic gate | truth table
---|---|---
`p || q` | or | OR gate <br> ![or.png](/images/logic-gates/or.png) | <table><thead><tr><th>$p$ </th><th> $q$ </th><th> $p \lor q$ </th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="F">F</td></tr></tbody></table>

### $\land$ conjunction

code | english | logic gate | truth table
---|---|---
`p && q` | and | AND gate <br> ![and.png](/images/logic-gates/and.png) | <table><thead><tr><th>$p$ </th><th> $q$ </th><th> $p \land q$ </th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="F">F</td></tr></tbody></table>

___

### $\downarrow$ joint denial

code | english | definition | logic gate | truth table
---|---|---
`!(p || q)` | not or | $p \downarrow q \equiv \lnot (p \lor q)$ | NOR gate <br> ![nor.png](/images/logic-gates/nor.png) | <table><thead><tr><th>$a$ </th><th> $b$ </th><th> $a \downarrow b$ </th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="F">F</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="T">T</td></tr></tbody></table>

### $\uparrow$ alternative denial

code | english | definition | logic gate | truth table
---|---|---
`!(p && q)` | not and | $p \uparrow q \equiv \lnot (p \land q)$ | NAND gate <br> ![nand.png](/images/logic-gates/nand.png) | <table><thead><tr><th>$a$ </th><th> $b$ </th><th> $a \downarrow b$ </th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="F">F</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="T">T</td></tr></tbody></table>

___

### $\rightarrow$ implication

Can be written as:  if p then q / if p, q / q unless ¬p / q if p / q whenever p / q follows from p / p implies q / p only if q / q when p / p is sufficient for q / q is necessary for p / a necessary condition for p is q / q is a necessary condition for p / a sufficient condition for q is p / p is a sufficient condition for q

code | english | definition | logic gate | truth table
---|---|---
`(!p) || q` | imply | $p \rightarrow q \equiv \lnot p \lor q$ | IMPLY gate <br> ![imply.png](/images/logic-gates/imply.png) | <table><thead><tr><th>$p$ </th><th> $q$ </th><th> $p \rightarrow q$ </th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="T">T</td></tr></tbody></table>



### $\leftrightarrow$ biconditional 

Can be written as: if and only if \ a is necessary and sufficient for b \ if a then b, and conversely \ a iff b

code | english | definition | logic gate | truth table
---|---|---
`p == q` | equals | $p \leftrightarrow q \equiv p \rightarrow q \land q \rightarrow p$ | XNOR gate <br> ![xnor.png](/images/logic-gates/xnor.png) | <table><thead><tr><th>$p$ </th><th> $q$ </th><th> $p \leftrightarrow q$</th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="F">F</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="T">T</td></tr></tbody></table>



### $\nleftrightarrow$ exclusive disjunction

Also noted as $\oplus$

code | english | definition | logic gate | truth table
---|---|---
`p != q` | not equals / exclusive or | $p \nleftrightarrow q \equiv \lnot (p \leftrightarrow q)$ | XOR gate <br> ![xor.png](/images/logic-gates/xor.png) | <table><thead><tr><th>$a$ </th><th> $b$ </th><th> $a \nleftrightarrow b$ </th></tr></thead><tbody><tr><td class="T">T</td><td class="T">T</td><td class="F">F</td></tr><tr><td class="T">T</td><td class="F">F</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="T">T</td><td class="T">T</td></tr><tr><td class="F">F</td><td class="F">F</td><td class="F">F</td></tr></tbody></table>

## all definitions

from [wikipedia: truth tabels](https://en.wikipedia.org/wiki/Truth_table#Binary_operations)

There are 16 operators that take 2 binary variables

$p$ | $q$ | $F$ | $\downarrow$ | $\nleftarrow$ |$\lnot p$| $\nrightarrow$ | $\lnot q$ | $\nleftrightarrow$ | $\uparrow$ | $\land$ | $\leftrightarrow$ | $q$ | $\rightarrow$ | $p$	| $\leftarrow$ | $\lor$ | $T$
:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:
<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>
<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>
<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>
<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>

$\nleftarrow$ = converse nonimplication

$\nrightarrow$ = material nonimplication

## functional completeness

NAND ($\uparrow$) is a functionally complete set, meaning all other operators can be defined only using NAND. For this reason computer cicuits often use only NAND gates to simplify manufacturing.