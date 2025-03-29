---
id: 1741963277-complex-system-architecture
aliases:
  - Complex System Architecture
tags: []
title: Complex System Architecture
---

- [GG HA](https://www.geeksforgeeks.org/harvard-architecture/)

Complex systems or Harvard Architecture have:
 - *Control Unit (CU)*: which handles the operations that the system has to perform
 - *Data Path*: executes arithmetic operations, it contains the [[1741963894-arithmetic-logic-unit---alu|Arithmetic Logic Unit - ALU]]
 - *Memories*: usually one memory containing both instructions and data, but the can be separated
 - *Input/Output*: devices that are external to the CU system

As there are more units that perform different tasks each unit has a dedicated bus:
 - **Data Bus**: it carries data form the memories, processor and I/O
 - **Data Address Bus**: it carries the address of data from the processor to the main memory
 - **Instruction Bus**: It carries instructions form the memories, processor and I/O
 - **Instruction Address Bus**: it carries the address of instructions from the CU to the memories 

![complex_system.png](assets/imgs/complex_system.png)

> [!TIP] Pro
> - Parallel instruction and data access: The separation of instruction and data memories allows parallel access, 
> improving overall efficiency.
> - Suitable for [[1741964924-real-time-systems|Real-Time Systems]] and low power applications

> [!IMPORTANT] Cons
> - Complexity due to having more units to manage

# References
- [[1741964101-general-purpose-architecture|General Purpose Architecture]]
