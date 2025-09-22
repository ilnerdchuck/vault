---
id: 1740668249-interleaved-multithreading
aliases:
  - Interleaved Multithreading
tags: []
title: Interleaved Multithreading
---

[[1740667904-multithreading|Multithreading]] technique. 

As the multithreading hypothesis that each thread has a relative data independence from each 
other, the processor switches thread every CPU cycle:
 
 1.  Cycle i: instruction j from thread A is issued.
 2.  Cycle i+1: instruction k from thread B is issued.
 3.  Cycle i+2: instruction e from thread C is issued.
 4.  Cycle i+3: instruction o from thread D is issued.
 5.  Cycle i+4: instruction j+1 from thread A is issued.
 6.  Cycle i+5: instruction k+1 from thread B is issued.
