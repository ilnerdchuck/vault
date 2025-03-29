---
id: 1740401450-out-of-order-execution
aliases:
  - Out Of Order Execution
tags: []
title: Out Of Order Execution
---

One of the possible solution for a [[1742056018-data-hazard|Data Hazard]].

> [!TIP] Solution
> Reorganize the order of the instructions so two consecutive instructions don't have any data 
> dependency.

The solution leads to an **out of order execution**

> [!DANGER] 
> If an in order execution is needed by the architecture, the commit of the instruction should be reorganized 

Example:

| Instruction       | 1   | 2   | 3   | 4   | 5   | 6   | 7   |
|--------------------|-----|-----|-----|-----|-----|-----|-----|
| i ADD R1,#5        | IF  | ID  | EX  | MEM | <span style="color:red">**WB**</span>  |     |     |     
| i+1 SUB R1,R2      |     | IF  | ID  | <span style="color:red">**EX**</span>  | MEM | WB  |     |     
| i+2 MUL R6,R7      |     |     | IF  | ID  | EX  | MEM | WB  |     

we can move the $MUL$ operation between the two dependent operations. 
