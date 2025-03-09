---
id: 1741004467-random-number-generation
aliases:
  - Random Number Generation
tags: []
---

# Random Number Generation

The genration of a random nmuber is bounded by the size of the architecture or the function that i use:
```c++
rand() % N;
```
after  some time will generate again the same number. this could be improved by adding the seed 
generator, but they will still repeat

Generating a random number is a finite set 
