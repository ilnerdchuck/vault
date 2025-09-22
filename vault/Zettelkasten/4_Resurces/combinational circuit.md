---
id: combinational circuit
aliases: []
tags:
  - VHDL
title: Combinational Circuit
---

Combinational circuits are nets with no memory (no registers) that react to the inputs 
as soon as they change and generates an output value. 

An example would be an half adder:
```vhdl
Library ieee; 
use ieee.std_logic_1164.all;
  
entity half_adder is
   port(a,b:in bit; sum,carry:out bit); 
end half_adder; 
 
architecture data of half_adder is
begin
    sum <= a xor b;  
    carry <= a and b;  
end data;

```
Implementaion:
- In VHDL to implement a combinational logic you can use two types of descriptions: [[Behavioural Description|behavioural description]] 
or [[Dataflow Description|dataflow description]]. While using a behavioural description as it uses a process we need to include in the sensitivity list all of the inputs.
- In Verilog we use [[Blocking Statement|blocking satement]] in an always block with a sensitivity list that includes all inputs or an assign statment.
