---
id: 1739626330-formal-models
aliases:
  - Formal Models
  - Formal Logic
tags: []
title: Formal Models
---

# Formal Models/Logic

It allows to make statements about objects and reason about their propeetries. Has
a grammar which is a set of syntax syntax rules which are used to compute formulas.

There are two categories of models: 
 - Logic: these logic uses [[1739626520-predicates|predicates]]:
   - [[1739630659-proposition-logic-boolean-algebra|Proposition logic (Boolean Algebra)]]: variables only have values inside `{0,1}`. 
   There are binary operators, and for each proposition we can only sentence if it is true or false
   - Predicate Logic (First-order Logic): Extension of Proposition Logic in which we can also quantify 
   variables by means of **quantifiers**: $\forall$ **FOR ALL**, $\exists$ **EXISTS**.   
   - Higher-Order Logic: Extension of First-order Logic in which quantifiers can also be used 
   to quantify about sets and functions 
   - [[1739706369-temporal-logic-modal-logic|Temporal Logic (Modal Logic)]]: While in other logics a statement is timeless, here we can also 
   express that a statement is true but may become false in the future and vice versa 
 - Automata: FSM, .. [not covered]

We use logic to formalize a property of a structure and check that the property holds

When we apply a model to verification, we represent the specification as a formula and the 
implementation either as a formula or a model. 
