---
id: 1739633064-conjunctive-normal-form-cnf
aliases:
  - Conjunctive Normal Form (CNF)
tags: []
---

# Conjunctive Normal Form (CNF)

Here we name $a,b,c$ as variables, and **LITERALS** as these variables direct or negated, 
such as $b$ and $\bar b$ .
 - A CLAUSE is a logical disjunction (OR) of literals.
Ex: $C_1=(\bar a +c)$, $C_2 = (a+\bar b +c)$

 - A Boolean Formula in CNF is a logical conjunction (AND) or clauses!
Ex: $(a+b+\bar c)(\bar a+c)(a+\bar b+c)$
 it is called Product of Sum (PS) form, we until now used Sum of products (SP) form

![[1739705858-satisfiability-problem-sat|Satisfiability Problem (SAT)]]

Basically now we are synthesizing in PS

It may not  be in canonical form

![[1739706139-davisputnamlogemannloveland-dpll-algorithm|Davis–Putnam–Logemann–Loveland (DPLL) algorithm]]
