---
id: 1739712358-linear-temporal-logic-ltl
aliases:
  - Linear Temporal Logic (LTL)
tags: []
title: Linear Temporal Logic (LTL)
---

# Linear Temporal Logic (LTL)

It models time as a totally ordered set $(S, \, <)$ isomorphic to $(N, \, <)$.

Let's take a set $AP$ which contains a number of atomic propositions and prove if they 
are true or false usiing a **Linear Time Structure** $M = (S, x, L)$:
 - $S$ set of states 
 - $x : N \rarr S$ is an infinite sequence of states $S_0$,$S_1$,$S_2 \dots$ 
 - $L : S \rarr 2^{AP}$ is a labeling function, each state with a set of atomic propositions in 
 $AP$ true state => when the labelign function is applied to a state it gives the only 
 proposition, in $AP$, true in that state   

![TLT_example.png](assets/imgs/TLT_example.png)
