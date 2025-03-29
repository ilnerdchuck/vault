---
id: 1740927090-pipelined-processor
aliases:
  - Pipelined Processor
tags: []
title: Pipelined Processor
---

Pipelining is an approach to parallel execution based on concurrently forming 
 different phases, these are the main ones: 
 - Instruction Fetch - IF 
 - Instruction Decode - ID 
 - Execution - EX 
 - Memory - MEM
 - Write Back - WB
for example and arm pipeline can have even more phases. 
The assumption on which the pipeline mechanism work is that the phases
are independent between different operations and can be overlapped, when this 
condition does not hold, the pipeline stalls (breaks) to enforce the dependency 

> [!TIP] Pro
> Multiple operations can be processed simultaneously with each operation at 
> different phase of it's processing. This increases drastically the throughput 
> of instructions.

| Instruction cycle | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |
|-------------------|-----|-----|-----|-----|-----|-----|-----|-----|
| i                 | IF  | ID  | EX  | MEM | WB  |     |     |     |
| i+1               |     | IF  | ID  | EX  | MEM | WB  |     |     |
| i+2               |     |     | IF  | ID  | EX  | MEM | WB  |     |
| i+3               |     |     |     | IF  | ID  | EX  | MEM | WB  |
| i+4               |     |     |     |     | IF  | ID  | EX  | MEM |

![pipeline_colored.png](assets/imgs/pipeline_colored.png)

Let's examine a simple pipelined machine: only one operation occurs in each phase at 
any given time:
 - One is fetched - IF 
 - One is decoded - ID 
 - an operation is executed - EX 
 - a result is written or read from memory - MEM
 - a result is written in the register file - WB

Further restrictions can be applied to a pipeline:
 - **Static Pipeline**: requires the processor to go trough all the stages/phases of 
 the pipeline whether required or not
 - **Dynamic Pipeline**: allows the bypassing of one or more of the stages/phases 
 of the pipeline depending on the requirements of the instruction.

# Pipeline breaks/stalls/ball
[Wiki](https://en.wikipedia.org/wiki/Pipeline_stall)
A pipeline stall is a delay in execution of an instruction in order to resolve 
a: 
 - Cache Miss
 - Hazards
    - [[1742056009-structural-hazard|Structural Hazard]]
    - [[1742056018-data-hazard|Data Hazard]]
    - [[1742056028-control-hazard|Control Hazard]]

# Pipeline improvements 
As pipelining dosen't allow to directly execute multiple instructions 
at the same time, there are other techniques that allows it. These implementations 
may use some combination of static or dynamic analysis to concurrently perform the actual 
evaluation phase of several different operations. This parallelism exploits concurrency 
at the computation level: **Instruction Level Parallelism**.

- [[1741185023-superscalar-processor|Superscalar Processor]] 
- Very Long Instruction Word (VLIW) 
    - Compiler performs Dependency Checking
    - Increased Code Size
    - lack of binary compatibility 
- Explicitly Parallel Instruction Computing (EPIC)
    - Dynamic VLIW
    - 128 bit word with 3 instruction in 41 bits and 5 bit with info on parallelism 
- [[1740667815-multi-core|Multi Core]]
- [[1740667904-multithreading|Multithreading]]

# References
- [[1740926625-dlx|DLX]]
