---
id: signal
aliases: []
tags:
  - VHDL
---

# Signal

It is used to hold any type of data. 
It represents an electrical connection, wire or bus. 
The declaration is done in the declarative part of the architecture.
They are shared among all the processes and statements inside the same architecture.
The assignment of the signal can be done in two ways:
 - Concurrent statement: done inside an architecture block
 - Sequential statement: done inside a [[process]] sequential statement,signals have now 
 two values a current value and a [[projected value]], the current value is replaced 
 by the projected value at the end of the process block.

```vhdl
architecture rtl of signal_example is
 -- signal declaration 
 -- signal SIG_NAME: TYPE (:= INIT_VALUE);
    signal sig_name: std_logic := 0;

begin
  process 
  begin
    -- signal assignment
    sig_name <= '1';
  end process;
end rtl;
```
