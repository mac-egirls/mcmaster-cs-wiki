---
title: 2.1 - data and programs.md
description: 
published: true
date: 2023-07-04T04:09:28.605Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:26.275Z
---

# Bits and Bytes
- bit - 0 or 1
- byte - 8 bits

# Data and Programs
- Stored program computer
- Bytes interpreted as instructions
- Bytes interpreted as standard data type

# Bytes, Words, and Order
How is data stared in memory?
- Often thing of it as an array
	- an array of cells, each cell has an index, each cell stores a byte
	- can query the memory at the index
- Reality, physical memory is not byte addressable, but word addressable
- Words
	- Size depends on architecture
	- 64x architecture - 4 bytes
	- 86x architecture - 8 bytes
- ***Little and Big Endian***
	- *Big Endian* - most significant bit is stored first
	- *Little Endian* - least significant bit is stored first

![](/images/20220915111801.png)
