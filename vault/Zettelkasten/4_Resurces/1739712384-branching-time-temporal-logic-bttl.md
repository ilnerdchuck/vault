---
id: 1739712384-branching-time-temporal-logic-bttl
aliases:
  - Branching Time Temporal Logic (BTTL)
tags: []
---

# Branching Time Temporal Logic (BTTL)

The logic is not linear so the structure of times becomes an infinite tree

As with PLTL there are state quantifiers $F$, $G$, $X$, $\cup$ to distinguish what happens inside one tree branch.

But we can also distinguish among various paths now (temporal timelines if you will), with the following **PATH QUANTIFIERS**:

- **$A$ ($\forall$): FOR ALL PATHS**
- **$E$ ($\exists$): THERE EXISTS A PATH**
**LTL is just BTTL with the $A$ quantifier always applied (to apply the formula to all possible futures)!**

Of course BTTL is more precise than LTL but requires us to “look more carefully”!

A very popular kind of BTTL is [[1739717419-1739717392-computationcomputation-tree-logic-ctl|Computation Tree Logic (CTL)]].
