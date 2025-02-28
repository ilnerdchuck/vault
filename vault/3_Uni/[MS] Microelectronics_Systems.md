---
id: "[MS] Microelectronics_Systems"
aliases: []
tags: []
title: "[MS] Microelectronics Systems"
---

### Sources 

Suggestes Textbooks:
 - Book Title

### Course info 
Professor: 
Email:
 

Exam Rules:
 - how the grading works 
 - Exam + Oral + Labs

# Recap 

ASIC
    - Data Memory 
    - Computation Unit (CU): Hierarchical FSM ?
    - Data Path: Arithmetic 

General Purpose
    microProcessor => ISA (Instruction Set Architecture)
    ![ISA_Arch.png](assets/imgs/ISA_Arch.png)

ISA Classification
    - Load/Store Architecture (RISC)
    - Register/Memory (CISC => x86, IBM)
    - Register+Memory (CISC => VAX)

note in real life only the 20% of the ISA is used 

CISC => Shorter programs, Reduced Memory, Reduced Silicon for Registers
    - Nowadays the CISC CPUs translate the instructions in RISC instructions
RISC 
    - Low number of instructions 
    - fixed length? What does it mean? All architectures have fixed length instructions 
    - Simpler addressing mode
    - Simpler and faster Hardware 
    - Uniform complexity 
    - Larger number of registers
    - Binary compatibility?: ability for the binary to be run on an another microP with the same arch
    - bad bandwidth to memory managment 

DLX Processor
 - 32 bit addressable memory
 - DLX register 
     - General purpose register (GPR)
     - Floating point register (FPR)
 - DLX data type 
     - Integer 
         - 32 bit word
         - 16 bit half word
         - 8  bit byte
     - Floating point types
 - DLX memory
     - Byte addressable in Big-Endian mode with 32 bit address
 - DLX instructions 
     - I-Type: immediate to register operation (LOAD/STORE, immeddiate, jump with reg)
     - R-Type: Register to register operation (ALU operation) 
     - J-Type: jump operation (ALU for new PC)
 - DLX Pipeline architecture
 ![DLX_Pipeline.png](assets/imgs/DLX_Pipeline.png)
     - DLX Operations
        - Instruction Fetch (IF):
            - IR <- MEM\[PC\]
            - NPC <- PC + 4
        - Instruction Decode (ID):
            - A <- REGS\[R₆...R₁₀\] 
            - B <- REGS\[R₁₁...R₁₅\]
            - Imm <- ((IR₁₆)¹⁶ ## IR₁₆...IR₃₁) what is this notation?: POW is replication(repeat the number) and ## is concatenation
                - replicate the MSB of the instruction and then concatenate with the Upper half of the IR
                ![IR_concat_replic.png](assets/imgs/IR_concat_replic.png)
        - Execution: 
            - Register-Register ALU: ALUOUT <- A OPCODE B
            - Register-Immediate ALU: ALUOUT <- A OPCODE Imm
            - Memory Reference ALU: ALUOUT <- A + Imm
            - Branch:
                - ALUOUT <- NPC + Imm
                - COND <- A op(== or !=) '0'
        - Write-Back(WB)
            - Register-Register <- ALU: REGS\[R₁₆...R₂₀\] <- ALUOUT
            - Register-Immediate <- ALU: REGS\[R₁₁...R₁₅\] <- ALUOUT
            - Load Instruction <- LMD (Load Memory Data): REGS\[R₁₁...R₁₅\] <- LMD
        - Memory Access/Branch Completion 
            - Program Counter updated (PC): PC <- NewPC (NPC)
            - Memory Reference:  
               - Load: LMD <- MEM\[ALUOUT\]
               - Store: MEM\[ALUOUT\] <- B
            - Branch: if (cond == true) PC <- ALUOUT

Sequential processors
![sequential_processor.png](assets/imgs/sequential_processor.png)
# Pipelined processors
![pipeline_processor.png](assets/imgs/pipeline_processor.png)
- Pipeline breaks => Stalls
    - Cache Miss
    - Hazards
        - Structural => Depends on resources
        ![structural_hazard.png](assets/imgs/structural_hazard.png)
        - Data
        ![data_hazard.png](assets/imgs/data_hazard.png)
        Solved trough
            - Forwarding
            - Out Of Order Execution
            - Register Renaming: RAW, WAR, WAW
        - Control
        ![control_hazard.png](assets/imgs/control_hazard.png)
            - Jump: Instruction Queue
            - Branch:
                - Delayed Branching
                - Branch Prediction
                    - Static
                    - Dynamic: 1 bit, 2 bit, Branch History Table (BHT)
(Pipeline improvements) Superscalar 
- Parallel Execution
- Limited Execution
- Dependency check expansive
- Very Long Instruction Word (VLIW) 
    - Compiler performs Dependency Checking
    - Increased Code Size
    - lack of binary compatibility 
- Explicitly Parallel Instruction Computing (EPIC)
    - Dynamic VLIW
    - 128 bit word with 3 instruction in 41 bits and 5 bit with info on parallelism 
Multiprocessors
- Many cores interconnected 
- May share resurces
- May rely on Multithreading (MT)
    - Classical MT (Time Division Multiplexing)
    - Block MT (Itamium)
        - Bunch of instruction from T.A.?
        - Bunch of instruction from T.B.?
    - Interleaved MT (SPARC)
        - i instruction j from T.A.?
        - i+1 instruction j from T.B.?
        - i+2 instruction j+1 from T.A.?
    - Simultaneous MT or Hyperthreading (Superscalar Ultrasparc T2 and newer intel until ALder lake)
        - i: $j_{TA}$, $k_{TB}$, $l_{TC}$ // we have multiple execution stages so we can execute the istructions jkl in parallel
        - i+1: $j+1_{TA}$, $k+1_{TB}$, $l+1_{TC}$

contex switch is costly we use (windowing) with register files 


# Niagara Ultrasparc T2 (For servers)

Multithreading Server App. Multicore RISC

# Pentium 4 



# Topic 3

