---
id: VHDL variable
aliases: []
tags:
  - VHDL
---

# Variable

It is used to hold any type of data. 
The declaration is done in the declarative part of a process.  
They can be used only inside a process and the scope is only inside the process they are declared in (local scope).
The assignment is done via the `:=` symbol. 
Their value is assigned immediately as the assignment statement occours (serialized order of execution).

```VHDL
architecture rtl of signal_example is
begin
  process 
 -- variable VAR_NAME : TYPE (:= INIT_VALUE);
    variable var_name : integer := 0;
  begin
    -- variable assignment
    var_name ;= 100;
  end process;

end rtl;
```
