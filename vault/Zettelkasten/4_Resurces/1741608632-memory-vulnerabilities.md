---
id: 1741608632-memory-vulnerabilities
aliases:
  - Memory Vulnerabilities
tags: []
title: Memory Vulnerabilities
---


Most Vulnerabilities derive form the memory and how the code is behaving. Usually they are 
driven by erroneous handling of the memory by the programmer1

All processes are kept in memory and every operation done to the memory can be 
a vulnerability:
 - .text: ***text segment*** contains binary executable instructions, it is **read-only**  
 - .data: ***initialized data segment*** portion of the virtual address that contains the global variables and 
 static variables initialized by the program, **read-only** and **writeable** parts
 - .bss: ***uninitialized data segment*** everything set to `0` or variables without an initialization
 - Heap: ***Dynamic memory allocation***, starts at the end of .bss and grows as needed using the 
 `malloc`, `realloc` and `free`
 - Stack: stores automatic variables, memory values and pointers with a [[1741624407-last-in-first-out---lifo|Last In First Out - LIFO]]
 policy 
 - Env: ***enviroment/arguments*** where system level variables used to control the programs are stores, such 
 as path, shell name etc..

In all cases the sizes and boundaries must be respected, the problem is the starting address that can vary, this 
is the main issue that leads vulnerabilities. 
![stack_example.png](assets/imgs/stack_example.png)

Usually a system has registers to handle the stack boudaries and operations:
 - **Extended Stack Pointer - ESP** top of the (low address) stack pointer
 - **Extended Base Pointer - EBP** bottom of the (high address) stack pointer
 - **Extended Instruction Pointer - EIP** points to the current memory location that needs to be executed 

[[1741609382-stack-operations|Stack Operations]]

# Vulnerabilities

