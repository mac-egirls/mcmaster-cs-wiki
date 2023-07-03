---
title: 1 - probability.md
description: 
published: true
date: 2023-07-03T02:40:02.160Z
tags: 
editor: markdown
dateCreated: 2023-06-15T03:56:50.317Z
---

# Probability
## Definition
- ***sample space*** - $S$ , is the set of outcomes of a random experiment.
- ***event*** - any subset of a sample space.

## Building New Events
Given events $E_1, E_2 \subseteq S$, the following are events:
1) $E_1 \cap E_2 = \{ x \in S : x \in E_1 \land x \in E_2 \}$ 
2) $E_1 \cup E_2 = \{ x \in S : x \in E_1 \lor x \in E_2 \}$ 
3) $E_1' = \{x \in S : x \not\in E_1 \}$.
4) $E_1 - E_2 = \{ x \in S : x \in E_1 \land x \not\in E_2 \} = E_1 \cap E_2^c$.

### Rules
1) $(E_1')'' = E_1$
#### Distributivity
2) $(A \cup B) \cap C = (A \cap C) \cup (B \cap C)$
3) $(A \cap B) \cup C = )A \cup C) \cap (B \cup C)$
#### De Morgan's Laws
4) $(A \cup B)' = A' \cap B'$
5) $(A \cap B)' = A' \cup B'$

## Definition
- events are ***mutually exclusive*** if they cannot occur at the same time.
$$\begin{aligned}
	E \cap F \equiv \emptyset \\
	P(E \cap F) = 0 \\
	P(E | F) = 0 \\
\end{aligned}$$
$$
\begin{aligned}
	E \cap F \equiv \emptyset \\
	P(E \cap F) = 0 \\
	P(E | F) = 0 \\
\end{aligned}
$$


### OR Rule
$$P(E \cup F) = P(E) + P(F)$$

## AND Rule
$$P(E \cap F) = P(E)P(F|E)$$

## Notation
$$P(E,F) = P(E \cap F)$$
- 2 events are ***statistically independent*** if $P(E \cap F) \equiv P(E)P(F)$
- $$P(E|F) \equiv P(E)$$
- ***mutually exclusive*** does not mean ***statistically independent***.
