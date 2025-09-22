---
id: 1740668221-block-multithreading
aliases:
  - Block Multithreading
tags: []
title: Block Multithreading
---

[[1740667904-multithreading|Multithreading]] technique. 

A bunch of instructions from a thread $A$ is executed. In case of a 
cache miss the processor doesn't waste time waiting but executes a bunch
of instructions from thread $B$. Once data for thread $A$ is ready, the CPU
switches back to the thread $A$.

 1.  Cycle i: instruction j from thread A is issued.
 2.  Cycle i + 1: instruction j + 1 from thread A is issued.
 3.  Cycle i + 2: instruction j + 2 from thread A is issued, which is a load instruction that misses in all caches.
 4.  Cycle i + 3: thread scheduler invoked, switches to thread B.
 5.  Cycle i + 4: instruction k from thread B is issued.
 6.  Cycle i + 5: instruction k + 1 from thread B is issued.
