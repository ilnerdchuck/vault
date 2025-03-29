---
id: 1740667904-multithreading
aliases:
  - Multithreading
tags: []
title: Multithreading
---


In computer architecture, multithreading is the ability of a central processing unit (CPU) 
(or a single core in a multi-core processor) to provide multiple threads of execution.
It is a technique also called *shared resource multiprocessing*. The principle is to exploit the 
fact that different threads in a process are independent in terms of data dependencies,
but **share resources**. 

The driving principle behind it is to make the best use of the silicon area. 

> [!TIP] Objective
> Remove [[1743178090-context-switching|Context Switching]] overhead as much as possible and reduce 
> the realized effect of branch and cache miss penalties

# Types of Multithreading
- [[1740668201-classical-multithreding|Classical Multithreading]]
- [[1740668221-block-multithreading|Block Multithreading]]
- [[1740668249-interleaved-multithreading|Interleaved Multithreading]] 
- [[1740668267-simultaneous-multithreading|Simultaneous Multithreading]]
- ... 
