---
id: 1739701289-ordered-binary-decision-diagram
aliases:
  - Ordered Binary Decision Diagram
tags: []
title: Ordered Binary Decision Diagram
---
[[1739633052-reduced-ordered-binary-decision-diagrams-robdds|Reduced Ordered Binary Decision Diagrams ((RO)BDDs)]]

# Ordered Binary Decision Diagram

It is a data sctructure used to represent boolean functions it has:
 - a unique starting node
 - internal nodes are boolean variables $x_i$ which are ordered between them (Ordered property), 
 different variables appear in the same order on all paths from the root  
 - each internal node has only 2 outgoing edges (boolean variable) labelled `1` if 
 $x_i=1$ or `0` if $x_i=0$
 - termianl nodes are labelled `1 (True)`  or `1 (False)`
![BDD_example.png](assets/imgs/BDD_example.png)
![BDD_from_truth_table.png](assets/imgs/BDD_from_truth_table.png)
