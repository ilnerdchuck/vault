---
id: 1740670007-architectural-scaling
aliases:
  - Architectural Scaling
tags: []
title: Architectural Scaling
---

Process to scale an architecture as needed and increasing it's performance.
[[1740676192-single-core|Single Core]] technologies doesn't scale well thus to increase 
the functionalities that a CPU can have [[1740669411-technology-scaling-ts|Technology scaling (TS)]] is not enough power density is an issue the problem is 
solved via [[1740667815-multi-core|Multi Core]] architectures ([[1740675665-mimd|MIMD]]) 
    - Only the needed core are working thus lowering the power density 
    - Good for multi tasking

Nowadays the classical [[1740676145-cpu|CPU]] connected to a single [[1740676136-bus|Bus]] 
is very limiting due to the low speeds to access the memory ([[1740670374-memory-wall|Memory Wall]]) 
As today applications are **Data Intensive** the access to memory are very frequent, the industry started to 
move the CPUs closer to larger memories and started specializing them and interconnect the cores with a 
[[1740681847-network-on-a-chip|Network on a Chip]] -> Like infinity fabric for AMD dies, they are called 
[[1740670519-hardware-accelerator|Hardware Accelerators (HA)]].

But having a specialized HA for every possible operation is very costly, so the industry added to the MCU an [[1740682029-fpga|FPGA]].
The accelerators can be implemented on the FPGA contained in the MPSoC (AMD Zynq) an perform the needed operations.
 Digital designers are searching ways to program at runtime the FPGA to suits the operations the cores/applications need to do =>Synthesize at runtime an accelerator (very difficult)

Having a Multi core design:
> [!CHECK]
> - Less Power Density => only the actual needed core are working 
> - can have different cores for different purpose 

> [!FAILURE]
> Parallelism and Concurrency issues => ensuring that all task are properly divided and executed in parallel
> Synchronization and Data Sharing => as there can be shared resources there can be [[1740682556-race-conditions|Race Conditions]], [[1740682568-deadlocks|Deadlocks]] and Cache coherence 

