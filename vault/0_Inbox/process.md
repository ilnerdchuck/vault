---
id: process
aliases: []
tags:
  - VHDL
---

# Process

A process is a concurrent statement: the code inside executed sequentially. 
It's structure is composed by: 
 - Sensitivity list 
 - Declarative part 
 - Sequential statement section

```vhdl
process_label : process(sensitivity list)
-- process declarative part
begin
    -- process sequential-statements ->
end process process_label;
```
- Sensitivity list: 

- Declarative part:
    - data object declaration
    - [[variable]]
    - [[signal]]

- Sequential Statements:
    - variable-assignment-statement
    - signal-assignment-statement
    - case statement
    - loop statement
    - if-else statement
    - assertion-statement
    - wait-statement

In a process statement we can only use `if then else` and `case when is` statements 
