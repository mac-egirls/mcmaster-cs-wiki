---
title: Truth Tables
description: 
published: true
date: 2023-08-20T00:11:47.741Z
tags: 
editor: markdown
dateCreated: 2023-06-18T00:17:37.087Z
---

# Truth Tables

A truth table shows all possible combinations of inputs for a logic equation on the left, and shows their corresponding outputs on the right. A table will have $2^n$ rows where $n$ is the amount unique variables in the equation.

For example: the and operator is shown as 

$p$ | $q$ | $p \land q$
:-:|:-:|:-:
T |T |T 
T |F |F 
F |T |F 
F |F |F 

More complex equations can be shown by breaking down the equation into smaller parts and showing each of them in the table, for example the equation $p \land q \rightarrow r$ can be shown in a truth table as seen below.

$p$ | $q$ | $r$ | $p \land q$ | $p \land q \rightarrow r$ |
:-: | :-: | :-: | :-: | :-: |
T | T | T | T | T |
T | T | F | T | F |
T | F | T | F | T |
T | F | F | F | T |
F | T | T | F | T |
F | T | F | F | T |
F | F | T | F | T |
F | F | F | F | T |

## resources

Tables can be generated using a  [python script](https://colab.research.google.com/drive/1syNsfL6h9hOoG_9PteqKuBVacz2Dnihh#scrollTo=zMGMcMKJZ03B&line=1&uniqifier=1) created by [Krish](https://github.com/Krish120003)