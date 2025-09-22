---
id: 1743170781-branch-prediction
aliases:
  - Branch Prediction
tags: []
title: Branch Prediction
---

Technique to mitigate [[1742056028-control-hazard|Control Hazards]]. 
The idea is that the CPU **guesses** whether the branch will be taken or not taken, thus choosing 
what the next fetched instruction would be. If the guess is correct then no time will be 
wasted, otherwise the pipeline has to be flushed.

There are two branch prediction methods 
 - Static
 - Dynamic: 1 bit, 2 bit, Branch History Table (BHT)

# Static Branch Prediction
This approach doesn't take into account the execution history. At compilation time 
chooses if the branch is: 
 - Always Taken
 - Never Taken
 - Make a decision based on the branch direction:
    - Branch is never taken for forward branches => if the address increases
    - Branch is always taken for backward branches => if the address decreases

> [!WARNING] Warning
> This is a cost effective solution: simple, but hasn't a high success rate.

# Dynamic Branch Prediction 
There are multiple strategies to improve the accuracy of prediction, they work by keeping track 
of the history of the conditional branches in a program. Based on the history the CPU can makes 
a decision the next time the same instruction is executed. This information is stored in a **High Speed storage**.
Solution to keep track of the branches history:
## **One bit**: 
 With a single bit all that can be recorded is only whether the previous execution of the instruction 
 was a taken or not taken branch. 
 > [!DANGER] Shortcoming
 > In case the branch is always taken (Ex for loop), with only one bit, an error in prediction 
 > will occur twice for each use of the loop: one upon entering and one upon exiting for a for loop.

## **Two Bits**: 
 Two bits are used to keep track of the result (of the branch if taken or not) of the two previous 
 predictions of the given instruction. There can be a multitude of schema to apply, a common one is to change 
 the prediction only if there have been two incorrect predictions in a row. This approach increases efficiency.
 > [!DANGER] Drawback
 > if the branch is predicted to be taken, the target instruction can't be fetched until the target address is 
 > computed

## **Branch History Table (BHT)** or **Branch Target Buffer (BTB)**: 
 It is a small cache associated with the instruction fetch stage. 
 Each entry in the table consists of three elements:
    - the address of the instruction itself 
    - some number of history bits 
    - address of the target instruction  
 
If a branch is taken some logic in the processor detects that and proceeds to fetch 
instructions from the target address. The **BHT** is treated as a cache: when an 
instruction is fetched a lookup is made in the table, if a match is found a prediction is made based on the 
state of the instruction and the instruction fetch target address is given based on if taken or not taken. 
When the branch instruction is executed, the execute stage signals the BHT logic which is the result and the 
history is updated. If an instruction is not in the BHT table it will replace one of the existing ones with one 
of the [[1743174935-cache-replacement-algorithms|Cache Replacement Algorithms]].





