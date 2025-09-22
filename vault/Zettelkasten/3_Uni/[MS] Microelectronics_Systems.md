---
id: "[MS] Microelectronics_Systems"
aliases: []
tags: []
title: "[MS] Microelectronics Systems"
---

### Sources

[VHDL](http://yang.zone/podongii_X2/html/technote/TOOL/MANUAL/21i_doc/data/fndtn/vhd/vhd10_3.htm)
Suggestes Textbooks:

- [Digital Integrated Circuits A Design Perspective by Rabaey, Chandrakasan, Nikolic](https://openlibrary.org/works/OL26437434W/Digital_Integrated_Circuits?edition=key%3A/books/OL35720852M)
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

## Microelectronic System

- [[1740733488-asic|ASIC]]
- [[1740926359-istruction-set-architecture|Istruction Set Architecture - ISA]]
- [[1740926407-cisc|CISC]]
- [[1740926402-risc|RISC]]
- [[1740927067-sequential-processor|Sequential Processor]]
- [[1740927090-pipelined-processor|Pipelined Processor]]
- [[1740667815-multi-core|Multi Core]]
- [[1740927250-register-window|Register Window]]
- [[1740928174-memory-hierarchy|Memory Hierarchy]]
- [[1741185023-superscalar-processor|Superscalar Processor]]
- Carry lookahead adder
- [[Register File]]

[[1740926625-dlx|DLX]]
[[1741169817-pentium-4-intel|Pentium 4 (Intel)]]
[[1741169857-ultrasparc-t2|UltraSPARC T2]]

- Body effect?

# Topic 3

# Laboratories

## Lab0/Lab1

### Vsim commands

### Synth commands

# Veerification Workshop presentation

## ASIC Design flow

![asic_design_and_verification.png](asic_design_and_verification.png)

Formal verification: verify that is compliant with the description

functional verification (gate-level verification):

- not good for large design => we use formal verificaition only

![verification_strategies.png](verification_strategies.png)

## Formal verification

> host: yann oddos

- mixed signal IPs: bbrings complexity in scaling, usable in many different platforms and  do performance analysis
  - verification challenges

- circuit design flow:
  - pre silicon
    - architecture
    - rtl & synthesis
    - Verification
    - place and route
  - post silicon
    - fabrication
    - testing and packaging
    - mass production

## Pre Silicon Verification

bottom up verification and then we test this products together:
    - make software simulation of devices to test out DUT to simulate the input signals
    - simulate also the consumers via software
    - build an abstraction model of the output signla to verify the correct behavior
    - then we unify this components to build a testbench

## UVM  based verification

UVM = Universal Verification Metodology

provides:

- Metodology
- library of system verilog classes

benefits:

- Standard testbench structure
- splits test scenarios from pin level protocols
- architecture modularity
- re-usability

the testbenches are based on agents:

- monitor: observe pins and pick their behavior
- driver: to control the circuit pins
- sequencer: connect the scenarios to the driver
- configuration: make the agent configurable
- sequence library: contains test scenarios

## [[1739623803-formal-verification|Formal Verification]]

equivalence checking:

- automated
- can only compare 2 design/models
model checking: unfolds all the possible path of a design => output is if all the properties have passed
- wide adoption and SVA learning curve is good
- state ecplosion/sun time for big design
symbolic simulation:
- good for data processing
- less common
theorem proving:
- powerful on parametric design
- mostlu manual require background in math and logic

## Co emulation  based verification

goal reduce verification time
idea: run the testbench on the computer and the DUT on a FPGA board

the outcome is a speedup in simualtion but there is an HW-SW overhead
