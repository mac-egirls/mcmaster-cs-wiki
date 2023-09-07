---
title: 10.6 - buffering.md
description: 
published: true
date: 2023-09-05T17:56:05.731Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:18.472Z
---

# Buffering
- System calls expensive: require synchronization
- Buffering calls: collect number of calls and perform simultaneously.
- Special procedures for read/write buffers
- On average we expect that a single call takes $M$ cycles for operations and $N$ cycles for overhead.
- $K$ calls then cost $K \times (M+N)$
- If we buffer, $K$ calls cost $K \times M + N$



  