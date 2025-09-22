---
id: 1739623803-formal-verification
aliases:
  - Formal Verification
tags: []
title: Formal Verification
---

[[1739623884-formal-methods|Formal Methods]]
[[1739624109-design-process|Design Process]]

[[1739628136-specification|Specification]]

# Formal Verification

Process of proving that a systems behaves according to it's 
specifications. 

The process is to use mathematical properties to become independent from 
the inputs, and prove it's validity => if the system has this property 
then is correct for all possible inputs. 

To prove the correctness trough formal verification you need:
 - Have [[1739626330-formal-models|Formal Models]]: have models for both specifications and implementation
 of the design
 - Use logic: mathematical approach
 - Interpret results 

 ![formal_verification.png](assets/imgs/formal_verification.png)

![formal_verification_comparison.png](assets/imgs/formal_verification_comparison.png)

Formal verification methods:
 - Interactive Method:
    - Theorem Proving: we prove any kind of relationship between a specification and implementation because
    we define it as theorem in a logic
 - Automated Method: 
    - Combinational equivalence checking: prove that two combinational design work the same, regardless 
    of the inputs.
    - Sequential Equivalence checking: Prove that two FSM are equivalent for all possible input sequences 
    (not just inputs).
    - Model Checking: We express a property of the model of our design and then check the property. 




