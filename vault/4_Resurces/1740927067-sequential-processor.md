---
id: 1740927067-sequential-processor
aliases:
  - Sequential Processor
tags: []
title: Sequential Processor
---

It is a type of scalar processor that processes a maximum of one instruction per cycle,
one after another. It requires that each instruction is executed to completion in sequence:
 the next instruction is not processed until all execution of the current one have been 
committed.

| Instruction cycle | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   |10   |
|-------------------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| i                 | IF  | ID  | EX  | MEM | WB  |     |     |     |     |     |
| i+1               |     |     |     |     |     | IF  | ID  | EX  | MEM | WB  |

> [!TIP] Pros
> Very simple conceptually and to implement

> [!DANGER] Drawbacks
> Executing each instruction sequentially has significant performance drawbacks: 
> a significant amount of time is spent in overhead and not in actual execution (think about
> a memory access to retrieve an operand that can take multiple clock cycles)
