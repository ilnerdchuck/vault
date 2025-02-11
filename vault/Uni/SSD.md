---
id: SSD
aliases: []
tags: []
title: Specification and Simulation of Digital Systems
---

## Exercises for the oral exam

ToDo: 
 - Convert all entries to notes

### 02
* What is projected value
* What you need to build a combinational circuit in VHDL: (have all signals in the sensitivity list) 
* Variables and Signal in VHDL (updated immediately meanwhile signals have a projected value)
* FSM Definitions: Formal and Other
* Differences between variables and signals in VHDL
* Process and sensitivity list in VHDL
### 03
* Delay models in VHDL: Inertia delay, transport delay and Delta delay. Why we use one or another and their keywords.
* Descrive the 'after' statement, tell if it is synthesizable or not
* What happens when one forgets and input in a sensitivity list 
### 04
* FSM with 2 processes and 1 process only
* Difference between one process description and two process description: differences in the sensitivity lists, is it possible to have only the clock in a sensitivity list?
* Mealy and Moore machines
* Asynchronous and synchronous reset, which one is better?
### 06
* Testbench in VHDL some questions 
### 07
* NRE cost and unit cost -> differences full custom and  FPGAs in terms of costs and volumes and also basic differences between them
* Non Returning costs
* Talk about FSM-D, name signals between controller and datapath
### 08
* Equivalent states
* State equivalence
* State reductions
* State equivalence reduction algorithms
* FSM equivalency, how can we prove that two FSM are equivalent?
* FSM equivalent states, when two states are equivalent, how we can verify when 2 states of an FSM are equivalent
* Describe the algorithm to prove that two FSMs are equivalent
* Product FSM for equivalence checking
* Difference between prime implicants and minterms
* Minterm, implicant, prime implicant and essential prime implicant definitions
* What is a prime implicant
* What is an essential prime implicant
* Boolean rule that makes it possible to expand literals in karnaugh map(ax+a = a )
* what is the boolean rule that allows us to merge implicants ok Karnaugh maps 
* Types of state encodings with advantages and disadvantages
* difference between implicants and minterms
### 09
* Types of assignment in Verilog
* Definition Purpose and meaning of REG in Verilog
* Definition Purpose and meaning of Wire in Verilog
* Blocking and non blocking assignment in Verilog
* Differences between VHDL and Verilog
* Parallel between process in VHDL and Always in Verilog
### 10
* BTL LTL differences and quantifiers
* Difference between LTL and BLT
* Definition of characteristic functions
* BDDs
* How to minimize a BDD
* Apply Operator
* Linear temporal logic and branching temporal logic, differences and wich operator they include
* BDD and ROBDD
* How to apply a logic operator to a BDD(or something like that, user didn´t know that one)
* FSM machine _product machine
* Branch temporal logic and it's operators (I guess BLT?)
* Describe the FSM product machine
* Reachability analysis
* What are BDDs and how complex are they depending on the number of Variables
* Can we reduce the size of a BDD? How?
* What are BDDs and what they are used Formal
* Complexity of BDDs
* Characteristic function - set and reachability analysis (what we use the operators on the sets for, how many states we can reach with the transition relation)
* What is clause (a term in a POS) 
* Formal verification on Embedded System design VHDL in particular the difference between a FSM with 2 processes and 1 process and what is the product ofFSMs for equivalence checking 
* All 6 temporal logic operators
* describe how to construct a BDD, how to reduce it and why do we call it a reduced ordered BDD
* Characteristic function
* Reachability: describe reachability analysis
* Definition on tautology and satisfiable formula
* Difference between branching time temporal logic and linear time temporal logic  (BTTL vs LTL)
* The product machine 
* LTTL and BTTL differences and operators
* FWD and BWD traversal 
* Equivalence checking (depth first, breadth first)
* clause, cnf dnf SoP Pos 
* operators in LTL
