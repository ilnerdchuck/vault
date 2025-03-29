---
id: 1741185023-superscalar-processor
aliases:
  - Superscalar Processor
tags: []
title: Superscalar Processor
---

It is a technique to improve a [[1740927090-pipelined-processor|Pipelined Processor]]. 
The principle is to enhance parallelism by adding **resources**: 
a superscalar processor executes more than one instruction during a clock cycle by dispatching 
multiple instructions to redundant functional units of the processor. Each functional 
unit is not a separate CPU but an additional resource within a single CPU like: and additional ALU, 
bit shifter or multiplier. An example could be

| Instruction cycle | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |
|-------------------|-----|-----|-----|-----|-----|-----|-----|-----|
| i LOAD            | IF  | ID  | EX  | MEM | WB  |     |     |     |
| i LOAD            | IF  | ID  | EX  | MEM | WB  |     |     |     |
| i+1 ADD           |     | IF  | ID  | EX  | MEM | WB  |     |     |
| i+1 ADD           |     | IF  | ID  | EX  | MEM | WB  |     |     |

The instruction fetch phase includes: branch prediction and checks for hazards giving as a 
result a stream of instruction to be executed according to the true data dependencies, this is the 
principle of [[1740401450-out-of-order-execution|Out Of Order Execution]]. 

Compared with a Pipelined Out of Order execution processor, a superscalar processor 
adds a scheduling instruction window that dynamically analyzes multiple instructions from 
the instruction stream. Even if they are executed in parallel, these instructions are treated 
in the same manner as in an [[1740401450-out-of-order-execution|Out Of Order]] pipelined processor.
**Before an instruction is issued for execution**, dependencies between the instruction itself and the 
previous instruction must be checked by the **hardware**. An example of instruction dispatching could be  
![instruction_sup_dispatching.png](assets/imgs/instruction_sup_dispatching.png)

The CPU chooses which instructions can run in parallel and uses the available hardware redundancies. 
For example 
$$
    a = b+c \\
    d = e+f \\

$$ 
can be dispatched to two different parallel arithmetic unit, while   

$$
    a = b+c \\
    d = a+f \\

$$ 
cannot. 

After their execution the instruction are reorganized in the sequential order and their result committed in order.

# Implementation 
From the implementation point of view a dedicated logic for determining true dependencies involving 
the registers is necessary, paired with a mechanism for communicating these values to where are needed 
during the execution. Also mechanism to commit the result of an instruction in the correct order at the end 
of the execution must be implemented. 

> [!WARNING]
> As the complexity is high due to dynamic scheduling logic, high-performance superscalar processors are 
limited to processing four to six instruction per cycle.

- Parallel Execution
- Limited Execution
- Dependency check expansive

# References 
- [[1740927090-pipelined-processor|Pipelined Processor]]
- [[1742056018-data-hazard|Data Hazard]]
- [[1742056028-control-hazard|Control Hazard]]
- [[1742056009-structural-hazard|Structural Hazard]]

