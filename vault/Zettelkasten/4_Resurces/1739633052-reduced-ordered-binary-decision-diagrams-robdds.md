---
id: 1739633052-reduced-ordered-binary-decision-diagrams-robdds
aliases:
  - Reduced Ordered Binary Decision Diagrams ((RO)BDDs)
tags: []
title: Reduced Ordered Binary Decision Diagrams ((RO)BDDs)
---

# Reduced Ordered Binary Decision Diagrams ((RO)BDDs)

It is based on [[1739701289-ordered-binary-decision-diagram|Ordered Binary Decision Diagram]], a ROBDD is a reduced version of a OBDD done 
by removing redundancy:
 - removal of reduntant tests
 ![redundant_test.png](assets/imgs/redundant_test.png)
 - Removal of a duplicate terminal node
 ![redundant_terminal_nodes.png](assets/imgs/redundant_terminal_nodes.png)
 - Removal of a duplicate non-terminal node
 ![redundant_non_terminal_nodes.png](assets/imgs/redundant_non_terminal_nodes.png)

We can analyze an example: 
 - OBDD
![original_OBDD.png](assets/imgs/original_OBDD.png)
![ex_removal_redundent_tesst.png](assets/imgs/ex_removal_redundent_tesst.png)
![ex_shared_subgraphs.png](assets/imgs/ex_shared_subgraphs.png)
![ex_redundant_test.png](assets/imgs/ex_redundant_test.png)
![ex_removing_terminal_nodes.png](assets/imgs/ex_removing_terminal_nodes.png)

ROBDD is always in a canonical form

## BDDs: Boolean Functions
We will now analyze how we can reduce the BDD using boolean functions. 
Starting from the *Shannon's expansion* theorem:  
$$
f\, op \, g = x'\cdot \left[f(x=0) \, op \, g(x=0)\right] + x\cdot[f(x=1)+g(x=1)]
$$

Given two ROBDDs $f$ and $g$ with roots $r_f$ and $r_g$ and leaves $l_f$ and $l_g$ then:
 - If $r_r,\,r_g$ are terminal nodes with labels $l_f=u,\,l_g=v$, create a terminal node labelled 
$w\triangleq l_f \,\, op \, \,l_g=u\,op\,v$ 
![BDD_red_1.png](assets/imgs/BDD_red_1.png)
 - If they are internal nodes labelled both $x$, create a node called $x$ whose left edge points to the BDD of $B \, op \, C$ and right edge to $B' \, op \, C'$ 
![BDD_red_2.png](assets/imgs/BDD_red_2.png)
 - If $r_f$ is labelled $x$ and $C=r_g$ is either a terminal node or is labelled $y \, |\,y>x$ in the ordering, create a node labelled $x$ which left edge points to $B\, op \, C$ and its right to $B' \, op \, C$
![BDD_red_3.png](assets/imgs/BDD_red_3.png)
 - If $r_g$ is labelled $x$ and $B=r_f$ is either a terminal node or is labelled $y\,|\,y>x$ in the ordering, create a node labelled $x$ which left edge points to $B\, op \, C$ and right one to $B\, op\,C'$
![BDD_red_4.png](assets/imgs/BDD_red_4.png)

Let's analyze an example:
![BDD_example_1.png](assets/imgs/BDD_example_1.png)
We compute the BDDs of every single operation:
 - $f_1=x_1+x_2$
 In this case the operator $op$ is the $OR$ operator ($\lor$)
 ![BDD_example_2.png](assets/imgs/BDD_example_2.png) 
 - we compute the BDD of $\overline{ x_1}$  
 ![BDD_example_3.png](assets/imgs/BDD_example_3.png)
 - $f_2=\overline{x_2}+x_3$ 
 ![BDD_example_4.png](assets/imgs/BDD_example_4.png)
 - $f_1 \cdot f_2$ 
 In this case the operator $op$ is the $AND$ operator ($\land$)
 ![BDD_example_5.png](assets/imgs/BDD_example_5.png)
![BDD_example_6.png](assets/imgs/BDD_example_6.png)
 And to get the ROBDD we just apply the reduction rules:
![BDD_reduced.png](assets/imgs/BDD_reduced.png)

## BDDs quatifiers





