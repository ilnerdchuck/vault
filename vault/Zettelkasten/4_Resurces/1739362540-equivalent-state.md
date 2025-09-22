---
id: 1739362540-equivalent-state
aliases:
  - Equivalent State
tags:
  - Digital Design
---

# Equivalent State

Two states are equivalent when:
 1. if their output is the same  
 2. if for every possible input generates the the same output 
 and the same state => they *transition* to equivalent states or 
 [[1739362571-identical-state|identical states]].

Example - Odd Parity Controlloer:
![equivalent_states.png](assets/imgs/equivalent_states.png)

1. `S0` and `S2` have the same output
2. Given `x=110`, starting from `S0` we get `y=0100` (states `S0`,`S1`,`S2`,`S2`),
instead starting from `S2` we get `y=0100` (states `S2`,`S1`,`S2`,`S2`).
We can say that “states `S0` and `S2` are equivalent” 

or by drawing the [[1739370933-state-transition-table|state transition table]]

|  `x`   | `S0` | `S2` |
| --- | -- | -- |
| `0` | `S0` | `S2` |
| `1` | `S1` | `S1` |

2. Both states when the inputs is equalt to `0` they conserve the state, 
meanwhile while the input `x` is equal to `1` they both transition
to the state `S1`.
As all conditions are satisfied we can say that `S0` and `S2` are equivalent. 
