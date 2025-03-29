---
id: 1742137949-register-renaming
aliases:
  - Register Renaming
tags: []
title: Register Renaming
---

One of the possible solution for a [[1742056018-data-hazard|Data Hazard]].

There can be two different data dependencies:
 - **True data dependency**: caused by data that is truly needed by the next operation
    - **read-after-write - RAW**: caused by a register read by one instruction after being written by another
 - **False data dependency**: caused by the reuse of the same registers ad the previous instruction
    - **write-after-read - WAR**: one instruction has to wait to write a register until another instruction 
    has to read the value
    - **write-after-write - WAW**: two instructions conflict with each other by trying to write in the same 
    register
 
the latter one never happens in architectures without branches all code is sequential, but nowadays 
mostly with branches and interrupts could happen that a write to the same register is needed without any reads.

> [!TIP] Solution
> Register renaming removes false dependencies by mapping the architectural registers of the program code 
> into physical registers on the processor. 

Thus the number of registers can be greater than the number of architectural registers. This 
also allows more instruction reordering to increase performance. Usually an on-chip **Register Alias Table - RAT**, usually 
based on a [[1742143744-content-addressable-memory---cam|Content Addressable Memory - CAM]], can be used to store 
which physical register each architectural register is currently mapped to.

![register_renaming_registers.png](assets/imgs/register_renaming_registers.png)

Example of all three dependencies: 

|             | Dest| Src | Data hazard|
|-------------|-----|-----|------------|
| ADD         | <span style="color:red">**R2**</span>  | R1  |         |
| MUL         | R3  | <span style="color:red">**R**</span><span style="color:green">**2**</span> |  <span style="color:red">**RAW**</span>    |
| MOV         | <span style="color:green">**R**</span><span style="color:yellow">**2**</span> | R4  |  <span style="color:green">**WAR**</span>    |
| BNZ         |     |     |         |
| MOV         | <span style="color:yellow">**R2**</span>  | #5  |  <span style="color:yellow">**WAW**</span>    |




|             | Dest| Src | Data hazard|
|-------------|-----|-----|------------|
| ADD         | <span style="color:red">**R2**</span>  | R1  |         |
| MUL         | R3  | <span style="color:red">**R2**</span> |  <span style="color:red">**RAW**</span>    |
| MOV         | R5  | R4  |            |
| BNZ         |     |     |            |
| MOV         | R6  | #5  |            |

But now i can reorder the instructions and move the $MOV$ (hehe move the move) between the $ADD$ and $MUL$. 
# References
- [[1740401450-out-of-order-execution|Out Of Order Execution]]
- [[1742137932-forwarding|Forwarding]]
