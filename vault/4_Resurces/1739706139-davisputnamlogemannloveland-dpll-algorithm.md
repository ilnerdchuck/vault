---
id: 1739706139-davisputnamlogemannloveland-dpll-algorithm
aliases:
  - Davis–Putnam–Logemann–Loveland (DPLL) algorithm
tags: []
---

# Davis–Putnam–Logemann–Loveland (DPLL) algorithm

This is an algorithm which starts from an ordering of the variables, and assigns values to each variables and looks for conflict or satisfiability.
![DPLL_init.png](assets/imgs/DPLL_init.png)


This algorithm is based on the UNIT CLAUSE RULE, which sets to 1 every single literal, one by one, and then iteratively applies a technique called BOOLEAN CONSTRAINT PROPAGATION (BCP) which allows to simplify the expression.

![DPLL_exec.png](assets/imgs/DPLL_exec.png)
