---
id: 1741793750-hardware-modeling
aliases:
  - Hardware Modeling
tags: []
title: Hardware Modeling
---

To be able to describe he hardware with languages or data structures: 
- Text based description: HDL (VHDL/Verilog), C++, SystemC
    - They allow a natural description as a Designer imagines it  
    - Multi level: able to describe both behavioural and Structural
    - Multi Abstraction: have the same language for different level of abstractions
- Abstract models:
    - Logic Level:
        - Graphs 
            - Good for circuit
            - Reasoning
            - Manipulation
            - Simulation
            - Verification
        - [[1741794080-generic-boolean-network|Generic Boolean Network]]
        - [[1739701289-ordered-binary-decision-diagram|BDD]]
        - [[1741794629-encoded-tables|Encoded Tables]]
        - [[1741794646-and-inverted-graph---aigs|And Inverted Graph - AIGs]]
    - Architectural Level:
        - Dataflow graph:
            - nodes: operations
            - edges: dataflow 

logic level:

This allows to compute some metrics on the description like the total area is the sum of all the 
$a_i$ ad the max delay the maximum sum among all path (also some of considerations of power) 
of the $d_i$ depending on the level of abstraction in which we are. 

Arch level:     
the size of the adders or delays of the operations 
