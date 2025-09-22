---
id: 1739712371-propositional-linear-temporal-logic-pltl
aliases:
  - Propositional Linear Temporal Logic (PLTL)
tags: []
---

# Propositional Linear Temporal Logic (PLTL)

Extension of [[1739712358-linear-temporal-logic-ltl|LTL]] with the addition of some Temporal Operators, given $p$,$q$ sentences:
 - $F\, p$  ($\diamondsuit p$): EVENTUALLY $p$, eventually $p$ will be true
 - $G\,p$ ($\square p$): ALWAYS $p$ is true, $p$ is always true
 - $X\,p$ ($O\,p$): NEXT TIME $p$, $p$ will be true at the next state 
 - $p\cup q$: $p$ UNTIL $q$, $p$ is true until $q$ becomes true 
 ![PLTL.png](assets/imgs/PLTL.png)

 PLTL syntax is very similar to [[1739630659-proposition-logic-boolean-algebra|Proposition Logic]], with the new operators meaning:
 - $F\,p $ abbreviates $(true \cup p)$
 - $G\,p$ abbreviates $\lnot F \lnot p$
 - $p \to F\,q$ means “if $p $ is true now then at some point in the future $q$ will be true”
 - $p \to F\,q$ means “if $p $ is true now then at some point in the future $q$ will be true”

As for semantics we have:
- $(M, \, x) \models p$ means “in structure $M$, formula $p$ is true of timeline $x$”
- We denote with $x^i$ a variable $x$ which starts at $s_i$ ($x^i=s_i, \, s_{i+1},\dots$)
- $(M, \,x)\models p \iff p\in L(S_0)$ for atomic propositions $p$
- $(M, \,x)\models p \land q \iff (M,x)\models p$ and $(M,x)\models q$
- $(M, \,x)\models\lnot p \iff$it is not the case that $(M, \,x)\models p$
- $(M, \,x)\models X\,p \iff x^1 \models p$ 
**Explanation**: Starting from the next state, $p$ is true
- $(M, \,x)\models F\,p \iff \exists \,j | (x^j \models p)$
**Explanation**: We can find an integer index $j$ such that starting from state $S_j$ the proposition holds on sequence $x^j=s_j,\,s_{j+1},\dots$!
**So basically there’s an index $j$ starting from which the proposition $p$ holds for all successive states $s_j$, $s_{j+1}$, etc…**
- $(M, \,x)\models G\,p \iff \forall j | (x^j \models p)$ 
**Explanation**: $x^j$ models $p$ for all possible $j$s, so **$p$ holds on all states**
- $(M, \,x)\models p \cup q \iff \exists j | (x^j \models p$ and $\forall k\in [0, j) \, \,(x^k\models p))$
**Explanation**: We can find a $j$ for which $q$ holds on $x^j$, and for all values preceding $j$ (which we call $k$ here), $p$ holds on $x^k$!
**Basically, for states with index $<j$, $p$  holds, while for states with index $\ge j$, $q$ holds!**

There’s a **DUALITY** between linear temporal operators:

- $\models G\lnot p \equiv  \lnot F\,p$
**Explanation**: Left Hand Side: $p$ is always false     Right Hand Side: there won’t ever be a state in which $p$ is true
- $\models F\lnot p \equiv \lnot G\,p$
**Explanation**: Left Hand Side: there will be a state where $p$ will be false     Right Hand Side: $p$ is not always true
- $\models X\lnot p \equiv \lnot X \, p$
**Explanation**: Left Hand Side: $p$ will be false at the next state   Right Hand Side: it will not be true that at the next state $p$ will be true

A formula $p$ is **SATISFIABLE** iff $\exists \, M=(S,\,x,\,L) \,|\, (M,x)\models p$!

- Any structure $(M,x)$ is called a **MODEL** of $p$!
- **When we check that a formula $p$ is satisfiable on a model $M$ we perform MODEL CHECKING!**

Example:
![PLTL_example.png](assets/imgs/PLTL_example.png)
We can express this protocol using PLTL language:

- **SAFETY PROPERTY**: Nothing bad will ever happen
    - $\forall t | (Validated(t) \to \lnot Validated(t+1))$
    - $G(Validated \to X\lnot Validated)$ (also written by exchanging $G\to \square, \, X\to O$)
    
    These are all possible ways to express that after the signal $Validated$ is $1$ at CC #$i$, it will be $0$ at CC #$i+1$!
    
- **LIVENESS PROPERTY**: Something good will eventually happen
    - $\forall t | \, Ready(t) \to \exists t'\ge t.\,Accepted(t')$
    - $G(Ready \to F\, Accepted)$
    
    These are possible ways to express that after some time the signal $Ready$ is true, also the signal $Accepted$ will become true!









