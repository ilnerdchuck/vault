---
id: 1740668201-classical-multithreding
aliases:
  - Classical Multithreading
tags: []
title: Classical Multithreading
---

[[1740667904-multithreading|Multithreading]] technique. 

It is based on the principle of **Time Division Multiplexing (TDM)**: 
a few milliseconds are dedicated to each thread, practice only one thread at the time 
is running on the hardware ([[1743178373-round-robin-scheduling|Round Robin Scheduling]])

![TDM.png](assets/imgs/TDM.png)

 1.  Cycle i: instruction j from thread A is issued.
 2.  Cycle i+1: instruction j+1 from thread A is issued.
 3.  Cycle i+2: instruction j+2 from thread A is issued.
 4.  Cycle i+3: instruction k from thread B is issued.
 5.  Cycle i+4: instruction k+1 from thread B is issued.
 6.  Cycle i+5: instruction k+2 from thread B is issued.

