---
title: 10.4 - device drivers.md
description: 
published: true
date: 2023-09-05T17:55:58.275Z
tags: 
editor: markdown
dateCreated: 2023-07-04T04:09:11.516Z
---

# Device Drivers
- Abstraction for dealing with devices
- Lower half: runs asynchronously
    - *low-level* part of the driver
    - comprised of a handler that is invoked when an interrupt occurs
- Upper half: provides OS interface to user-space programs (system calls)
    - *high-level* of the driver
    - programs are in here like main.c programs
    - Takes calls and puts it in a queue (*shared variables*) for things for the device to do
- Communication via shared variables, buffers, and mutually exclusive execution (mutex)
![](/images/20221201155642.png)

#### Example
![](/images/20221201205928.png)

# System calls and standard libraries
System calls provide access to devices, but this access is *raw*. Library functions provide wrappers.
| system call | libstdc wrapper |
| ----------- | --------------- |
| open        | fopen           |
| close       | fclose          |
| read        | fread           |
| write       | fwrite          |
| seek        | fseek           |

