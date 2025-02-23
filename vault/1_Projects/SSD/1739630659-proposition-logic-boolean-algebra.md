---
id: 1739630659-proposition-logic-boolean-algebra
aliases:
  - Proposition logic (Boolean Algebra)
tags: []
title: Proposition Logic (Boolean Algebra)
---

# Proposition Logic (Boolean Algebra)

We define $P$,$Q$ and $R$ as symbols representing propositions.
 - A proposition is Atomic if can't be further broken down into smaller propositions 
 - A proposition can either have two values: `True` or `False`

Operators of propositional logic
 - **NEGATION OPERATOR**: $\lnot P$ 
 - **CONJUNCTION OPERATOR**: $P \land Q$
 - **DISJUNCTION OPERATOR**: $P \lor Q$
 - **IMPLICATION OPERATOR**: $P \to Q$
 It’s equivalent to $(\lnot P)\lor Q$.
 - **EQUIVALENCE OPERATOR**: $P \iff Q$ (”P if and only if Q”)
 It’s equivalent to $(P\land Q) \lor ((\lnot P)\land (\lnot Q))$.

We can express the semantics of a proposition by using a truth table:
| P   | Q   | $\neg$P  | P $\land$ Q | P $\lor$ Q | P $\to$ Q | P $\iff$ Q |
|---|---|---|---|---|---|---|
| t   | t   | f   | t   | t   | t   | t   |
| t   | f   | f   | f   | t   | f   | f   |
| f   | t   | t   | f   | t   | t   | f   |
| f   | f   | t   | f   | f   | t   | t   |

As we can see the $\land$ operator is an **AND**, $\lor$ an **OR**, $\iff$ a **XNOR** gate and
$\to$ has no corresponding gate because it is based on the order of the values.

An **interpretation**  is a function from the propositional symbols to $\{t,f\}$

Defined a formula $F$ we can analyze if it is:
 - Satisfiable (Consistent): if it's true under at least one interpretation, we note with 
 $I \models F$ the fact that $I$ satisfies the formula $F$ ($I$ is a model of $F$) if $F$
 is true under $I$.
 - Unsatifiable (Inconsistent): if it's false under all interpretations 
 - Valid (Tautology): if it's true under all interpretations

> [!INFO] Theorem
> A formula $F$ is still valid if $\neg F$ is unsatifiable.
> it is noted as $\models F$
> ![FV_theorem_formula.png](assets/imgs/FV_theorem_formula.png)
>So, the problem to determine if a formula $F$ is satisfiable or valid is NP-complete, because it would require to list (test) $2^n$ interpretations (we have to test $n$ interpretations, each of which gives $2$ results: $t$ or $f$)!

to implement formal verification methods we need to represent formulas as data structures:
 - [[1739633052-reduced-ordered-binary-decision-diagrams-robdds|Reduced Ordered Binary Decision Diagrams ((RO)BDDs)]] which are always in canonical form 
 - [[1739633064-conjunctive-normal-form-cnf|Conjunctive Normal Form (CNF)]] which may not always be in canonical form



[[1739632677-canonical-form|Canonical Form]]
