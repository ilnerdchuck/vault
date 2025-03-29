---
id: 1743170765-delayed-branching
aliases:
  - Delayed Branching
tags: []
title: Delayed Branching
---

Technique to mitigate [[1742056028-control-hazard|Control Hazards]]. The idea is to 
let the CPU do work during the cycles where it should stall. 

> [!TIP] Solution
> The CPU executes always the instruction after the **JUMP/Branch** instruction, then it is  
> committed on the effective behavior of the **JUMP** instruction.

The instruction after the branch instruction is called <span style="color:green">*Branch Delay Slot*</span>

| Instruction cycle | 1   | 2    | 3    | 4   | 5   | 6 | 7 | 8 |
|-------------------|-----|------|------|-----|-----|---|---|---|
| i ADD             | IF  | ID   | EX   | MEM | WB  |   |   |   |
| i+1 JUMP          |  | IF | ID | <span style="color:red">**EX**</span>| MEM  | WB  |   |   |
| i+2 MUL           |  |  | IF   | <span style="color:green">**ID**</span>  | EX  | MEM  | WB  |   |

The **MUL** instruction is only executed when the branch is ***not taken***, the compiler/programmer has the task 
to find a suitable instruction to be moved from it's original place into the <span style="color:green">*Branch Delay Slot*</span>
to be executed regardless the outcome of the branch (for example the index increment of a for loop).

. Ex 
| Instruction     | 1   | 2   | 3   | 4   | 5   | 6 | 7 | 8 |
|-----------------|-----|-----|-----|-----|-----|---|---|---|
| i  <span style="color:green">**MUL R3,R4**</span>    | IF  | ID  | EX  | MEM | WB  |   |   |   |
| i+1 SUB R2,#1   |     | IF  | ID  | EX  | MEM | WB  |   |   |
| i+2 ADD R1,R2   |     |     | IF  | ID  | EX  | MEM | WB  |   |
| i+3 BEZ target  |     |     |     | IF  | ID  | <span style="color:red">*EX*</span>  | MEM | WB  |   |
| i+4 MOV R1,#10  |     |     |     |     | IF  | <span style="color:red">*ID*</span>  | EX  | MEM |

In this case the **MOV** instruction should be executed only when the branch is not taken, the **MUL**
is executed every time the loop is performed and doesn't influence the subsequent instructions it can be moved 
to the <span style="color:green">*Branch Delay Slot*</span>.
Thus the final sequence of execution would be 

```mermaid
flowchart LR
  SUB --> ADD
  ADD --> BEZ
  BEZ --> MUL
  MUL --> MOV
```
