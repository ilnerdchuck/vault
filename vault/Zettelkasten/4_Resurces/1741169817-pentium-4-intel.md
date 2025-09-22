---
id: 1741169817-pentium-4-intel
aliases:
  - Pentium 4 (Intel)
tags: []
title: Pentium 4 (Intel)
---

![p4_die_shot.png](p4_die_shot.png)

The Pentium 4 is an Intel microprocessor. It is a [[1740926407-cisc|CISC]] architecture 
but it is structured as a [[1740926407-cisc|CISC]] outer shell and an internal 
[[1740926402-risc|RISC]] superscalar micro-architecture. 

![p4_cisc_chell.png](assets/imgs/p4_cisc_chell.png)

> [!IMPORTANT]
> The purpose of the CISC shell is to maintain **binary compatibility**
> and the necessity of a RISC processor is to increase performance

This architecture is based on the translation of CISC instructions called **macro-Instruction** 
into simpler and RISC compatible instructions called **micro-Instruction** or ***uops***. Let's analyze an 
example:
 - **macro-Instructions**: add add BX to mem(AX) and store in mem(AX) 
 $$
    ADD\ (\%AX),\ \%BX
 $$
 - **uops** translation result:
 $$
    LD\ \%R2, (\%R1)\\ 
    ADD\ \%R3, \%R2\\ 
    ST\ \%R3, (\%R1)\\ 
 $$
the macro-instruction wants to add a value to a memory location, in x86 assembly it is 
dove via a single instruction. Meanwhile in a RISC architecture the same operation is performed by:
 - getting the value from the memory 
 - performing the addition
 - storing the result in memory 

> [!IMPORTANT] uops optimizations
> the goal of the uops is to reduce the complexity of the decode and execution unit. As the 
> instructions are less and simpler the optimizations are more straightforward then a CISC

> [!IMPORTANT] Futureproof
> An architecture that performs this type of translations can change it's internal RISC 
> design without changing the outer interface

while the example and most macro-instructions can be translated form one to one or 
three uops, some complex instructions require a lot of uops, thus to optimize the 
translation an instruction ROM is introduced. The content of the ROM is the translation 
of the complex macro-Instruction, the content of the ROM is called **microcode**, an example
of complex instructions could be the boot, reset or interrupt handlers.

# General Organization
The general operations performed by the P4 are:
 - Fetch macro-instruction **In Order**
 - Translate each macro-instruction into a stream of uops 
 - Execute the uops with a superscalar **Out of Order** organization 
 - Commits the result of the uops **In Order** 

The whole pipeline is 20 cycles long an it is organized in four main sections:
 - [[#In Order Front End]] pipeline: fetches the instructions to be executed. It has an accurate  
 [[1743170781-branch-prediction|Branch Prediction]], the predicted instruction address is used to 
 fetch instructions form the **Level 2 (L2)** cache an translate them in uops to be placed 
 in a **Level 1 (L1)** cache for the OoO engine to be picked this cache is the [[#Trace Cache]].  
 - [[#Out of Order Engine]]: is where the instructions are prepared for execution. The instructions 
 are severely reordered to allow a faster execution, as soon as their operands are ready. This 
 [[1740401450-out-of-order-execution|OoO]] allows resources such as the ALU and the cache 
 to be kept busy as much as possible. This block also contains a [[#Retiring]] block which reorders 
 the instructions back to the original flow, it also tells to the [[#BTB]] informations on the execution 
 to keep track of the branches.
 - [[#Integer and Floating point unit]] execution pipeline: is where the instructions are executed. 
 It includes a **[[1743240510-register-file|Register File]]** to store the integers an floating-points
 data operands that the instructions needs in order to execute. It also contains a **Level 1 (L1)** data
 cache to perform load and store operations.
 -[[#Memory Subsystem]]: it contains the **L2** cache and system bus. The purpose of the L2 cache is 
 to store both instructions and data that cannot fit in the **Execution Trace Cache** and the **L1**
 cache. The external system bus is connected to the backside of the L2 cache and it is used to 
 access the main memory in case of: miss, replace and access to I/O. 

General layout:
![p4_general layout.png](p4_general_layout.png)
![misprediction_p4.png](misprediction_p4.png)
![general_arch_p4.png](general_arch_p4.png)

# In Order Front End 
It consists in several units it has:
 - [[#Instruction TLB]]
 - Front end branch predictor [[#BTB]]
 - An [[#IA-32 Instruction Decoder]]
 - [[#Trace Cache]]
 - [[#Microcode ROM]]
 - [[#Trace Cache BTB]]


## Trace Cache
The Trace Cache is the primary or Level 1 (L1)
instruction cache of the Pentium 4 processor and delivers
up to three uops per clock to the out-of-order execution
logic.
It stores already decoded instructions removes the IA-32 decoding from the main
execution loop. Typically the instructions are decoded once and placed in the 
Trace Cache and then used repeatedly from there like a normal instruction cache on
previous machines. 
> [!IMPORTANT]
> The IA-32 instruction decoder is only used when the machine misses the Trace Cache and needs
> to go to the L2 cache to get and decode new IA-32 instruction bytes.

> [!IMPORTANT]
> The uops that come from the Trace Cache and the microcode ROM are buffered in a simple, in-order uop
> queue that helps smooth the flow of uops going to the out-of-order execution engine.


### Trace Cache BTB
There is a smaller BTB compared to the general front-end [[#BTB]] as it's main purpose is to 
handle the predicts in a much smaller subset of the program currently handled by the Trace Cache. 

### Microcode ROM
it is used to translate complex IA-32 instructions. When a complex instruction needs to be decoded, 
the Trace cache jumps to the microcode ROM which issues the uops needed for the translations. 


## Instruction TLB
This module and the [[#BTB]] are used when there is a cache miss in the [[#Trace Cache]].
The ITLB translates the instruction pointer ([[1741965815-virtual-memory|virtual Memory]]) to a 
physical address to access the L2 cache, it includes also a page protection mechanism.
In case of a miss in the TLB will cause the system to load a page in cache before continuing.
> [!IMPORTANT]
> It will be the OS to handle the page fault


## BTB
The instruction pre-fetcher is driven by the BTB to know what to fetch next ([[1743170781-branch-prediction|Branch Prediction]]).

## IA-32 Instruction Decoder
It receives IA-32 instruction bytes from the L2 cache 64-bits 
at a time and decodes them into uops. This single instruction decoder 
can decode at a maximum rate of one IA-32 instruction per clock cycle. 
Many IA-32 instructions are converted into a single uop, and others 
need several uops to complete the full operation. If more than four 
uops are needed to complete an IA-32 instruction, the decoder 
sends the machine into the microcode ROM to do the instruction. 
Most instructions do not need to jump to the microcode ROM to complete.

## Fetch and Decode Flow (Queue)
Using the address determined by the [[#Trace Cache BTB]] the trace cache is read, in case of a miss 
the needed instruction is loaded from the L2 cache.
The data read from the L2 cache then flows through the front-end pipeline to be decoded and loaded into the trace
cache. If there is a trace cache hit, the trace cache delivers up to 3 uops per cycle. Some uops
read from the trace cache are actually pointers to uop routines stored in the microcode ROM.
In this case, the ROM is read and it begins feeding uops into the execution pipeline instead.
This allows macro-instructions that must be translated into large numbers of uops to not take
up space in the trace cache.

# Out of Order Engine 
The Out of Order Engine takes care of allocation, renaming and scheduling functions. 
This is where the instruction are reorddered to increase the performance. By looking at a larger 
number of instruction from the program at once it can usually find more ready to execute independent 
instructions. 

## Allocator
The first step of the freshly decoded uops is to be allocated in an entry of the **reorder buffer ROB** for the requested 
resurce. The entries are kept, in program order, until each uop is retired or discarded. The P4 ROB has 
126 entries, once this entries have been filled the allocation step must stall the uops and wait 
for space to become available. 
> [!IMPORTANT]
> Once a uops is allocated it is allowed to flow in the pipeline

## Register Renaming
The register renaming logic renames the IA-32 8 register entries in a 128 [[1743256012-register-alias-table---rat|Register Alias Table - RAT]] physical registers. This also allows the handling of [[1742056018-data-hazard|Data Hazards]], as renaming 
removes false data conflicts. 
> [!IMPORTANT]
> The renaming logic keeps the most up to date value each register, so that a new instruction 
> can know where to get the correct instance of the needed registers 

![rat_p4.png](rat_p4.png)
It allocates the ROB entries and the result data Register File (RF) entries
separately. The ROB entries, which track uop status, consist only of
the status field and are allocated and deallocated
sequentially. A sequence number assigned to each uop
indicates its relative age. The sequence number points to
the uop’s entry in the ROB array.

## uOPS Scheduling
The uop schedulers determine when a uop is ready to execute by tracking 
its input register operands. The uop schedulers are what allows the instructions 
to be reordered to execute as soon as they are ready, while still
maintaining the correct dependencies from the original program.
The P4 has two sets of structures to aid in uop scheduling: 
 - the uop queues (FIFO):
    - Memory operations queue: holds all the load and store operations 
    - General queue: holds all others uOPS  
    this is to improve performance when memory operations need to wait for the data:
    meanwhile the general queue uOPS are executed. Thus the queues are FIFO but can be executed 
    OoO. 
 - the actual uOP schedulers:  A lot of schedulers can be used but all behave somewhat 
    the same: they determine when uops are ready to execute based 
    on the readiness of their dependent input register operand 
    sources and the availability of the execution resources. At each cycle 
    they will check which registers have valid data and dispatch the uOPS.

> [!IMPORTANT]
> uOPS enter the scheduler in order but can be dispatched as soon as their operands are ready 
> thus OoO

## Dispatching
There are four dispatch ports: 
 - two execution unit in port 0 and 1: they can dispatch up to two operations per clock cycle.
 The fast ALU can schedule at every edge of the clock or at half of the main clock cycle, meanwhile
 the other schedulers can only schedule one operation per clock cycle.
 - Load 
 - Store

![dispatch_p4_ports.png](dispatch_p4_ports.png)

# Retiring
This step is performed after the rest of the execution unit pipeline has finished, but it refers to 
the OoO block ad the result of the operations needs to be checked and committed in order. For example if the 
instruction was a branch the actual result is compared with the predicted one. The front end [[#BTB]] and 
[[#Trace Cache BTB]] are updated with the branch behavior. If the branch was mispredicted, the [[#Trace Cache BTB]] is 
signaled to read uOPS from the correct address. If the prediction was correct no events occur and the 
uOP is retired. Once retired the uOPS results are committed to the current architectural state in the RAT 
and all the resources allocated are released.

# Integer and Floating point unit

The execution units are designed to optimize
overall performance by handling the most common cases
as fast as possible. There are several different execution
units in the P4 microarchitecture: the units used to
execute integer operations include the low-latency integer
ALUs, the complex integer instruction unit, the load and
store address generation units, and the L1 data cache.

![p4_execution_units.png](assets/imgs/p4_execution_units.png)

The Integer and floating-point register files sit between
the schedulers and the execution units. Each register file also has
a multi-clock bypass network that bypasses or forwards
just-completed results, which have not yet been written
into the register file, to the new dependent uops ([[1742137932-forwarding|Forwarding]]).
There are three separate processor for the actual uOPS:
 - **Integer Execution Unit (IEU)**: performs all the integer operations and branches. 
 - **Floating Point Unit (FPU)**: performs all the floating point and [[1740675970-simd|SIMD]] operations. 
 - **Memory Execution Unit (MEU)**: that performs loads and stores operations
All execution units are connected to the [[#Level 1 (L1) Data Cache]] with a 
Data Translation Lookaside Buffer (DTLB) for the virtual to physical address translation. 
When an execution is completed, if there is a result it will be committed to the register files.

# Memory Subsystem
The memory subsystem includes the
Level 2 (L2) cache and the system bus. The L2 cache
stores data that cannot fit in the Level 1 (L1) caches. The
external system bus is used to access main memory when
the L2 cache has a cache miss and also to access the
system I/O devices.

## Level 1 (L1) Data Cache 
The Level 1 (L1) data cache is an 8K-byte cache that is
used for both integer and floating-point/SSE loads and
stores. It is organized as a 4-way set-associative cache
that has 64 bytes per cache line. It is a write-through
cache, which means that writes to it are always copied
into the L2 cache. It can do one load and one store per
clock cycle. The latency of load operations is a key aspect of processor
performance. This is especially true for IA-32 programs
that have a lot of loads and stores because of the limited
number of registers in the instruction set.


## Level 2 Instruction and Data cache
The L2 cache is a 256K-byte cache that holds both
instructions that miss the Trace Cache and data that miss
the L1 data cache. The L2 cache is organized as an 8-way
set-associative cache with 128 bytes per cache line.
The L2 cache has a write-back cache policy.

Associated with the L2 cache is a hardware pre-fetcher that
monitors data access patterns and prefetches data
automatically into the L2 cache. It attempts to stay 256
bytes ahead of the current data access locations. This
prefetcher remembers the history of cache misses to
detect concurrent, independent streams of data that it tries
to prefetch ahead of use in the program. The pre-fetcher
also tries to minimize prefetching unwanted data that can
cause over utilization of the memory system and delay the
real accesses the program needs.

# In depth analysys
 - P4 adder
 etc....
