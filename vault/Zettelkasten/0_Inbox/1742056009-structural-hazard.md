---
id: 1742056009-structural-hazard
aliases:
  - Structural Hazard
tags: []
title: Structural Hazard
---
It is a pipeline break caused by resource conflicts: the architecture of a processor can include only one instance of a 
functional block (Ex only a single divider, multiplier, IF handler ...). 
> [!DANGER] Cause
> If two instructions that need to be executed requests both the same functional block, for example the divider, 
> whether they have, or not, any other dependency, one of the two instructions has to wait until the completion 
> for the current instruction. 

Thus this is purely a hardware related hazard. 

Ex Memory related structural hazard:

| Instruction cycle | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |
|-------------------|-----|-----|-----|-----|-----|-----|-----|-----|
| i LOAD            | IF  | ID  | EX  | <span style="color:red">**MEM**</span> | WB  |     |     |     |
| i+1 ADD           |     | IF  | ID  | EX  | MEM | WB  |     |     |
| i+2 MUL           |     |     | IF  | ID  | EX  | MEM | WB  |     |
| i+3 SUB           |     |     |     | <span style="color:red">**IF**</span>  | ID  | EX  | MEM | WB  |

> [!TIP] Solution
> Increase the hardware at disposal, change the memory layout: for example in a use a Hardware architecture to separate 
> Instruction memory from Data Memory

# References
- [[1741185023-superscalar-processor|Superscalar Processor]]
