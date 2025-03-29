---
id: 1740926359-istruction-set-architecture
aliases:
  - Istruction Set Architecture
tags: []
title: Istruction Set Architecture
---

It is a model that defines how software can control the CPU. An ISA 
defines:
 - Supported Instructions
 - Data Types
 - Registers
 - How to manage the main memory: addressing modes, [[1741965815-virtual-memory|Virtual Memory]]
 - Input/Output Model 

The scheleton of how a ISA works is: 
 - **Fetch**: retrives the istruction form memory and stores in a register called **Instruction Register - IR** 
 - **Decode**: the istruction is decoded by the control unit => the operands are prepared for the arithmetic 
 unit in the data path
 - **Execute**: the isntruction is executed and the result stored, meanwhile the **Program Counter - PC**

A general ISA instruction could be:
$$
    op\ source,\ destination
$$
 - op: is the operation to be performed
 - source: operand from which we read the value
 - destination: operand where the result will be stored, somethimes it could be 
 also a source operand

> [!IMPORTANT]
> The order or how many operands are there, depends on the implementation as stated above

ISA can be classified on how the instructions interacts with the memories:
 - Load/Store Architecture - L/S ([[1740926402-risc|RISC]]): all operands must be loaded into registers 
 before an execution can take place, Ex:
    $$
        ADD\ R1, R2
    $$
 - Register/Memory - R/M ([[1740926407-cisc|CISC]] => x86, IBM): instructions have one operand in memory and one in memory, Ex:
    $$
        ADD\ %EAX, 0x123456789
    $$
    the second operand is a memory address, during the decode phase it is retreived form the memory and 
    given to the alu for execution, the destination is the %EAX register
 - Register+Memory - R+M ([[1740926407-cisc|CISC]] => VAX): instruction can have **both** operands in memory or 
 registers or any combination of them. It is a generalization of the R/M format, but complicates 
 the decoding process => the interpretation of the instruction is slow, but it makes an excellent use of 
 the memory and bud bandwith.

## Trivia
The tradeoff in instruction set is an area/time compromise: the R/M and R+M architectures 
offers a more concise program representation using fewer instructions compared to and L/S 
architecture. Thus programs occupy less space in memory and smaller istrucitons caches can 
be used. But the variable instruction size makes decodign more difficult, it requires more 
circuitry.

> [!TIP]
> in real life only the 20% of the (ISA or written program?) is used 

# References
- [[1741966246-register-list|Register List]]
- [[1741969179-cisc-vs-risc|CISC vs RISC]]
