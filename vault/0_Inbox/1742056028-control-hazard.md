---
id: 1742056028-control-hazard
aliases:
  - Control Hazard
tags: []
title: Control Hazard
---

Control hazard are caused by jump or branch instructions.

| Instruction cycle | 1   | 2    | 3    | 4   | 5   | 6 | 7 | 8 |
|-------------------|-----|------|------|-----|-----|---|---|---|
| i ADD             | IF  | ID   | EX   | MEM | WB  |   |   |   |
| i+1 JUMP          |  | IF | ID | <span style="color:red">**EX**</span>| MEM  | WB  |   |   |
| i+2 MUL           |  |  | IF   | <span style="color:red">**ID**</span>  | EX  | MEM  | WB  |   |
| i+3 MOV           |  |  |    | <span style="color:red">**IF**</span>  | ID  | EX  | MEM  | WB  |

The instruction following the jump is fetched (MUL), but when the jump is taken the pipeline must be flushed.


> [!TIP] Solutions for unconditional branches 
> - Use instruction queues so that instructions are fetched before they are needed.
> - The fetch unit has the ability to recognize jump instruction and generate the target address,
> by computing the address of the jumps allows the instruction fetch to continue from the new address directly 
> ![istruction_fetch_queue.png](assets/imgs/istruction_fetch_queue.png)

> [!WARNING]
> The first solution doesn't take into account conditional branches 

> [!TIP] Solutions for conditional branches 
> There are two possible solutions: [[1743170765-delayed-branching|Delayed Branching]] and [[1743170781-branch-prediction|Branch Prediction]].
