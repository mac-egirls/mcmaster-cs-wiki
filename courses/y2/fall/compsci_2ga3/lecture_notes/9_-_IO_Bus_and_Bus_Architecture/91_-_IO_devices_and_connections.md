---
title: 9.1 - IO devices and connections.md
description: 
published: true
date: 2023-07-04T04:10:59.260Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:10:56.646Z
---

# IO Devices
![](/images/20221124103451.png)
- IO device is an external circuit connected to the CPU via digital signals
- primary function: data transfer
- follow the fetch/store data paradigm.

# How do we transfer data?
| Parallel                              | Serial                                      |
| ------------------------------------- | ------------------------------------------- |
| multiple data lines                   | single data line                            |
| number of lines = interface width     | transfer data in series, one item at a time |
| transfer multiple bits simultaneously |                                             |

![](/images/20221124104215.png)

- ***latency*** - travel time from sending to receiving an item
- ***throughput*** - how many things will go through at a time

# How do we transfer data?
| Parallel                                    | Serial                                      |
| ------------------------------------------- | ------------------------------------------- |
| multiple data lines                         | single data line                            |
| number of lines = interface width           | transfer data in series, one item at a time |
| transfer multiple bits simultaneously       |                                             |
| lower latency per word - can send in one go | higher latency - word sent sequentially,    | 
| potentially higher throughput,              | but possibly higher rate of data transfer   |
| but possible issues with interference       |                                             |

# Clocks and Synchronization
![](/images/20221124104855.png)
- A clock signal is required to disambiguate between bits
- clock signal may be explicitly transmitted on dedicated line
- some interfaces clockless: synchronization sequence plus implied clock

> ***Parallel and Serial Interfaces***
> Interface is in the context of a computer and an exteranl device.
> 
> - ***Parallel Interface***: allows for transfer of multiple bits of data simultaneously.
>     - contains many ***interface wires***, each wire containing one bit of data
>     - ***interface width*** - refers to the number of parallel wires an interface uses.
> - ***Serial Interface***: Only one bit of data transfer at a time.

- Example: serial interface at 9600bps (9.6 kHz)
- Sender and receiver need to have agreed on frequency

# Communication Directionality
Communication channel can be classified based on what type of information exchange it allows
- Single direction: data only flows from $A \to B$, never $A \leftarrow B$.
- Half-duplex. Allows either $A \to B$ XOR $A \leftarrow B$
- Full-duplex: Allows $A \leftrightarrow B$

# Multiplexing
- For transferring larger data size over a narrow channel
![](/images/20221124110150.png)

