---
title: Logical Operators
description: boolean operators, truth tables, and basic circuits
published: true
date: 2023-06-17T12:35:58.416Z
tags: logic, computer architecture
editor: markdown
dateCreated: 2023-06-17T12:35:58.416Z
---

# Logical Operators

A Logical operator takes in $n$ truth values, and returns a truth value 

## Truth Tables

Logical operators are defined by showing all possible combinations of inputs, and their corresponding outputs for an operator in a table.

For example: the and operator is shown as 

$p$ | $q$ | $p \land q$
:-:|:-:|:-:
<p class="T">T</p> | <p class="T">T</p> | <p class="T">T</p>
<p class="T">T</p> | <p class="F">F</p> | <p class="F">F</p>
<p class="F">F</p> | <p class="T">T</p> | <p class="F">F</p>
<p class="F">F</p> | <p class="F">F</p> | <p class="F">F</p>

## Operator Names

### Basic Operators

all other operators can be defined using these three operators that are most commenly used

symbol | name | english representation | (typical) code representation
---|---|---|---
$\lnot$ | negation | not | !p
$\land$ | conjunction | and | p && q
$\lor$ | disjunction | or | p \|\| q

### Other Common Operators

symbol | name | english representations
---|---|---
$\rightarrow$ | implication | <ul><li>if A then B</li><li>if A, B</li><li>B unless ¬A</li><li>B if A</li><li>B whenever A</li><li>B follows from A</li><li>A implies B</li><li>A only if B</li><li>B when A</li><li>A is sufficient for B </li><li>B is necessary for A </li><li>a necessary condition for A is B</li><li>B is a necessary condition for A </li><li>a sufficient condition for B is A</li><li>A is a sufficient condition for B </li></ul>
$\leftrightarrow$ or $\equiv$ | biconditional | <ul><li>if and only if</li><li>a is necessary and sufficient for b</li><li>if a then b, and conversely</li><li>a iff b</li><li>not exclusive or</li></ul>
$\oplus$ | exclusive disjunction | <ul><li>exclusive or</li><li>xor</li></ul>

### Other Operators

symbol | name | english representations
---|---|---
$\downarrow$ | joint denial | not or
$\nleftarrow$ | converse nonimplication |
$\nrightarrow$ | material nonimplication |
$\uparrow$ | alternative denial | not and



## all definitions

from [wikipedia: truth tabels](https://en.wikipedia.org/wiki/Truth_table#Binary_operations)

There are 16 operators that take 2 binary variables

$p$ | $q$ | $F$ | $\downarrow$ | $\nleftarrow$ |$\lnot p$| $\nrightarrow$ | $\lnot q$ | $\oplus$ | $\uparrow$ | $\land$ | $\leftrightarrow$ | $q$ | $\rightarrow$ | $p$	| $\leftarrow$ | $\lor$ | $T$
:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:
<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>
<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="T">T</p>
<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="T">T</p>
<p class="F">F</p>|<p class="F">F</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>|<p class="F">F</p>|<p class="T">T</p>

### trivia

NAND ($\uparrow$) is a functionally complete set, meaning all other operators can be defined only using NAND. For this reason computer cicuits often use only NAND gates to simplify manufacturing.

## logic gates

todo