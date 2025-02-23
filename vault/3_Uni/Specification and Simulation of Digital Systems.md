---
id: SSD
aliases: []
tags: []
title: Specification and Simulation of Digital Systems
---

## Exercises for the oral exam

ToDo: 
 - Convert all entries to notes

### 02 VHDL Combinational Logic
* What is projected value [[projected value]];
* What you need to build a combinational circuit in VHDL [[combinational circuit]] 
* Variables and Signal in VHDL [variable](0_Inbox/1739292539-NJVE.md), [signal](0_Inbox/1739292535-ZTRC.md)
* Differences between variables and signals in VHDL
* Process and sensitivity list in VHDL
### 03 VHDL Combinational Datapath Components
* Delay models in VHDL: Inertia delay, transport delay and Delta delay. Why we use one or another and their keywords.
* Descrive the 'after' statement, tell if it is synthesizable or not
> - Inertia delay: it deletes pulses that are less than a threshold long 
> - Transport delay: it propagates all pulses all input events are propagated to output signals
> - Delta delay: no propagation delays are specified, a small delay is inserted by the simulator to add correct ordering 
> of events
> ![delays.png](assets/imgs/delays.png)
* What happens when one forgets and input in a sensitivity list 
### 04 Sequential Logic
* FSM with 2 processes and 1 process only
* Difference between one process description and two process description: differences in the sensitivity lists, is it possible to have only the clock in a sensitivity list?
* Mealy and Moore machines
* Asynchronous and synchronous reset, which one is better?
### 06 Testbench & Assertions
* Testbench in VHDL some questions 
### 07 Embedded RTL Design
* NRE cost and unit cost -> differences full custom and  FPGAs in terms of costs and volumes and also basic differences between them
* Non Returning costs
* Talk about FSM-D, name signals between controller and datapath
### 08 Optimization Techniques
* [[1739362540-equivalent-state|Equivalent State]]
* [[1739362495-state-reduction|State reduction]]
- [[1739362571-identical-state|Identical State]]
* [[1739363674-state-reduction-algorithms|State Reduction Algorithms]]
- [[1739465355-state-encoding|State Encoding]]
- [[1739465556-output-encoding|Output Encoding]] 
* Difference between prime implicants and minterms
* Minterm, implicant, prime implicant and essential prime implicant definitions
* What is a prime implicant
* What is an essential prime implicant
* Boolean rule that makes it possible to expand literals in karnaugh map(ax+a = a )
* what is the boolean rule that allows us to merge implicants ok Karnaugh maps 
* Types of state encodings with advantages and disadvantages
* difference between implicants and minterms
### 09 Verilog
* Types of assignment in Verilog: 
    - [[Blocking Statement|blocking satement]] 
    - [[1739355937-non-bocking-statement|non bocking statement]]
* Definition Purpose and meaning of REG in Verilog
    - [[1739356114-register-data-type|Register Data Type]]
* Definition Purpose and meaning of Wire in Verilog
    - [[1739356158-net-data-type|Net Data Type]]
* Differences between VHDL and Verilog
* Parallel between process in VHDL and Always in Verilog
    - [[process|Process]]
    - [[1739356217-always|Always]]
# 10 Formal verification
[[1739623803-formal-verification|Formal Verification]]
## Questions:
* operators in LTL
> - $F\,p$  abbreviates $(true \cup p)$
> - $G\,p$ abbreviates $\lnot F \lnot p$
> - $p \to F\,q$ means “if $p$  is true now then at some point in the future $q$ will be true”.
> - $G(p\to F \,q)$ means “whenever $p$ is true, $q$ will be true at some subsequent moment”

* BTL LTL differences and quantifiers
> LTL:
>  - LINEAR TIME STRUCTURE $M=(S, \,x,\,L)$:
>  - $S$ is a **SET OF STATES**
>  - $x:N\to S$ is an **INFINITE SEQUENCE OF STATES** $S_0, \, S_1, \dots$
>  - $L:S\to 2^{AP}$ is a **LABELLING FUNCTION** which outputs in each state the set of atomic propositions in $AP$ true at that state!
>  - $F\, p$ / $\diamondsuit p$: EVENTUALLY $p$ ([F]inally)
>  - $G\,p$ / $\square p$: ALWAYS $p$ is true ([G]lobally)
>  - $X\,p$ / $O\,p$: NEXT TIME $p$ 
>  - $p\cup q$: $p$ UNTIL $q$
> 
> BTL:
> - instead of being on one timeline it has multiple branches, 2 new quantifiers for the branches:
>   - **$A$ / $\forall$: FOR ALL PATHS**
>   - **$E$ / $\exists$: THERE EXISTS A PATH**
> - Computetion Tree Logic (CTL) are used to represent all possible paths 



* BDD and ROBDD: BDD and how to minimize them
> - unique starting node 
> - internal ordered variables in all path of the graph 
> - each node has 2 outgoing edges 
> - terminal nodes labeled with $0$ or $1$
>
> we reduce them by applying 3 rules:
> - Removal of redundant test (nodes that that whatever the decision will not affect the outcome)
> - Removal of duplicate terminal node 
> - Removal of a non-terminal node (merging sub-graphs)

* Complexity of BDDs: 
> - linear 
> - Exponential, always exp for multipliers

* Apply Operator: merging algorithm
> Used to apply a boolean operator to a BDD Tree, 4 cases:
> ![apply_case_1.png](assets/imgs/apply_case_1.png)
>  ![apply_case_2.png](assets/imgs/apply_case_2.png)
>  ![apply_case_3.png](assets/imgs/apply_case_3.png)
>  ![apply_case_4.png](assets/imgs/apply_case_4.png)


* What is clause ([[1739633064-conjunctive-normal-form-cnf|CNF]])
> A term in a PS 

* All 6 temporal logic operators

- FSM Formal definition
> **Formally, a FSM is a 6-tuple** $M=(I, \, O, \, S,\,\delta,\,\lambda,\,S_0)$:
> - **$I$ INPUT ALPHABET**
> - **$O$ OUTPUT ALPHABET**
> - **$S$ SET OF STATES**
> - **$\delta$ NEXT-STATE RELATION** $\delta : S\times I \to S$.
> Using another syntax we could write $\delta \sube S\times I \times S$.
> - **$\lambda$ OUTPUT RELATION** ( $\lambda : S \to O$ for a Moore machine , $\lambda: S\times I \to O$ Mealy) .
> Using the other syntax, for Moore we have $\lambda \sube S\times O$, for Mealy $\lambda \sube S\times I \times O$
> - **$S_0$ SET OF INITIAL STATES**

* Describe the FSM product machine
> ![product_machine.png](assets/imgs/product_machine.png)
> - The input space is the original input space $I$
> - The output space is $\{0,1\}$ because we want to compare the two FSMs, so we put a XOR at the end
> - The set of states of $M$ is the cartesian product of the set of states of $\displaystyle M'$$M'$$M''$$M',M''$$S'\times S''$
> - The $\delta$ (state) function of $M$ is the concatenation of the next-state relations $\delta'$ and $\delta''$
> - The output $\lambda$ function is the same for the two FSMs

* FSM equivalency, how can we prove that two FSM are equivalent?
* Describe the algorithm to prove that two FSMs are equivalent
* Reachability analysis: describe reachability analysis
> - we start from an initial state 
> - until all reachable states are reached compute:
>   - $\delta$ for the next state 
>   - Check the output of each state 
> ![reach_analysis.png](assets/imgs/reach_analysis.png)

* Equivalence checking (depth first, breadth first)
> - Depth Visit
> ![depth_visit.png](assets/imgs/depth_visit.png)
> - Breadth Visit
> ![breadth_visit.png](assets/imgs/breadth_visit.png)

* Characteristic function (used in state equivalence checking)
> A formula that can represent a set of states: by applying the function to a state it returns if the state is in the states of a machine or not 


* FSM Definitions: Formal and Other
* Definition on tautology
> - tautology = if a $F$ormula is valid under all interpretations 

* Satisfiable Formula ([[1739705858-satisfiability-problem-sat|SAT]])
> a formula is Satisfiable if there exists and interpretation of non contracdicting boolean variables which
> satisfies the formula by setting a literal in each clause 

* FWD and BWD traversal  
> - **FORWARD TRAVERSAL**: Start from initial states and traverse forwards to check whether “bad” states are reachable!
> - **BACKWARD TRAVERSAL**: Start from bad states and check whether initial states can reach them!


* clause, cnf, dnf?, SP PS 

