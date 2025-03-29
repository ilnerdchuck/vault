---
id: 1740668267-simultaneous-multithreading
aliases:
  - Simultaneous Multithreading
  - Hyperthreading
tags: []
title: Simultaneous Multithreading
---

[[1740667904-multithreading|Multithreading]] technique. 

Also called **Hyperthreading** by Intel. 
    
It is used in [[1741185023-superscalar-processor|Superscalar Processors]]: the 
processor issues instructions form multiple threads every CPU cycle:


1. Cycle i: instructions j and j + 1 from thread A and instruction k from thread B are simultaneously issued.
2. Cycle i + 1: instruction j + 2 from thread A, instruction k + 1 from thread B, and instruction m from thread C are all simultaneously issued.
3. Cycle i + 2: instruction j + 3 from thread A and instructions m + 1 and m + 2 from thread C are all simultaneously issued.

