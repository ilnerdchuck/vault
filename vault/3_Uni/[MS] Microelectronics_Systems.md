---
id: "[MS] Microelectronics_Systems"
aliases: []
tags: []
title: "[MS] Microelectronics Systems"
---

### Sources 
[VHDL](http://yang.zone/podongii_X2/html/technote/TOOL/MANUAL/21i_doc/data/fndtn/vhd/vhd10_3.htm)
Suggestes Textbooks:
 - [Digital Integrated Circuits A Design Perspective by Rabaey, Chandrakasan, Nikolic ](https://openlibrary.org/works/OL26437434W/Digital_Integrated_Circuits?edition=key%3A/books/OL35720852M)
 - [CMOS VLSI Design by NEIL H.E. Harris, David Weste](https://openlibrary.org/works/OL9402217W/CMOS_VLSI_DESIGN?edition=key%3A/books/OL10460377M)
 - [Computer architecture a quantitative approach 5th ed. by John L. Hennessy](https://openlibrary.org/works/OL16184111W/Computer_architecture?edition=key%3A/books/OL25060968M)
### Course info 
Professor: Mariagrazia Graziano 
Email: [mariagrazia.graziano@polito.it](mailto::mariagrazia.graziano@polito.it)
Office: 4th floor room 32 

Lab Professors:
 - Giovanna
    - Email:
    - only organization related topic
 - dd
    - Email:
    - technical questions

Exam Rules:
 - how the grading works 
 - Exam + Oral + Labs

# Recap 

[[1740733488-asic|ASIC]]
    - Data Memory 
    - Computation Unit (CU): Hierarchical FSM ?
    - Data Path: Arithmetic 

General Purpose
    microProcessor => [[1740926359-istruction-set-architecture|Istruction Set Architecture]] (Instruction Set Architecture)
    ![ISA_Arch.png](assets/imgs/ISA_Arch.png)

ISA Classification
 - Load/Store Architecture ([[1740926402-risc|RISC]])
 - Register/Memory ([[1740926407-cisc|CISC]] => x86, IBM)
 - Register+Memory ([[1740926407-cisc|CISC]] => VAX)

> [!TIP]
> in real life only the 20% of the (ISA or written program?) is used 

CISC 
 - Shorter programs, Reduced Memory, Reduced Silicon for Registers
 - Nowadays the CISC CPUs translate the instructions in RISC instructions
RISC 
 - Low number of instructions 
 - fixed length? What does it mean? All architectures have fixed length instructions 
 - Simpler addressing mode
 - Simpler and faster Hardware 
 - Uniform complexity 
 - Larger number of registers
 - Binary compatibility?: ability for the binary to be run on an another microP with the same arch
 - bad bandwidth to memory management 

- [[1740927067-sequential-processor|Sequential Processor]]
- [[1740927090-pipelined-processor|Pipelined Processor]]
- [[1740667815-multi-core|Multi Core]]
- [[1740927250-register-window|Register Window]]
- [[1740928174-memory-hierarchy|Memory Hierarchy]]

![[1740926625-dlx|DLX]]
[[1741169857-ultrasparc-t2|UltraSPARC T2]]
[[1741169817-pentium-4-intel|Pentium 4 (Intel)]]

[[1741185023-superscalar-processor|Superscalar Processor]]
- Carry lookahead adder
[[Register File]]

we need multiply and accumulate for AI (they are only weighted sums)




# Topic 3
# Laboratories 
## Lab0/Lab1
### Vsim commands
### Synth commands
