---
id: 1739363752-implication-table
aliases:
  - Implication Table
tags: []
title: Implication Table
---

[[1739363674-state-reduction-algorithms|State Reduction Algorithms]]

# Implication Table

An algorithm to reduce the number of states in a [[1739371932-finate-state-machine|FSM]]. 

> [!Algorithm]
> 1. Create a matrix $X$ that enumerates each possible state pairs => <font color="green"> **Implication Table**</font>
> 2. Simplify the matrix by noticing that the lower part and upper part  of the matrix divided by the 
diagonal are equal and the diagonal would indicate a pair with itself => take only the lower 
part of the matrix
> 3. Each cell $X_{i,j}$ is filled as following: <br>
    - if the states $S_i$ and $S_j$ denoted by the $i$,$j$ cell have a different output then we cross
 out the cell <br> 
    - if the states $S_i$ and $S_j$ denoted by the $i$,$j$ cell have the same output we keep the cell
> 4. we fill the remaining cells with wich next state should be equal to the sate pair to become equivalent:
if the state $S_i$ has $S_k$ as next state and $S_j$ has $S_p$ as next state the equivalency condition is that 
$S_k = S_p$
> 5. Eliminate cells until no more can be eliminated based on: <br>
    - if the cell $(i,j)$contains a pair of states which one of them is in another eliminated cell we cross out also 
 the $(i,j)$ cell
> 6. Each pairs that survived the elimination process implies that thoose states are equivalent 

![implication_table.png](assets/imgs/implication_table.png)

> [!TIP]
> This algorithm doesn’t work by proving formally that two states are equivalent, but rather it eliminates all possible pairs of states which are not equivalent! 

Let's make an example by reducing a sequency matching machine:
 - one input `x`
 - one output `z`
 - generate 1 as aotput when the sequences `010` or `110` are recognized on the input 

| Input Sequence | Current State | Next State (`x=0`) | Next State (`x=1`) | Output (`x=0`) | Output (`x=1`) |
|---------------|--------------|------------------|------------------|-------------|-------------|
| Reset        | S₀          | S₁              | S₂              | 0           | 0           |
| 0            | S₁          | S₃              | S₄              | 0           | 0           |
| 1            | S₂          | S₅              | S₆              | 0           | 0           |
| 00           | S₃          | S₀              | S₀             | 0           | 0           |
| 01           | S₄          | S₀              | S₀             | 1           | 0           |
| 10           | S₅          | S₀              | S₀             | 0           | 0           |
| 11           | S₆          | S₀              | S₀             | 1           | 0           |

> [!STEP]
> 1. Draw the implication table
> 2. take only the lower half
> 3. Each cell $X_{i,j}$ is filled as following: <br>
    - if the states $S_i$ and $S_j$ denoted by the $i$,$j$ cell have a different output then we cross
 out the cell <br> 
    - if the states $S_i$ and $S_j$ denoted by the $i$,$j$ cell have the same output we keep the cell
> 4. we fill the remaining cells with wich next state should be equal to the sate pair to become equivalent:
if the state $S_i$ has $S_k$ as next state and $S_j$ has $S_p$ as next state the equivalency condition is that 
$S_k = S_p$

|          |           |           |         |         |         |         |
| -------- | --------- | --------- | ------- | ------- |-------- | ------- |
| S1  | S1-S3  |       |       |       |       |  |
|     | S2-S4  |       |       |       |       |  |
| S2  | S1-S5  | S3-S5 |       |       |       |  |
|     | S2-S6  | S4-S6 |       |       |       |  |
| S3  | S1-S0  | S3-S0 | S5-S0 |       |       |  |
|     | S2-S0  | S4-S0 | S6-S0 |       |       |  |
| S4  |  X     |  X    | X     | X     |       |  |
| S4  |  X     |  X    | X     | X     |       |  |
| S5  | S1-S0  | S3-S0 | S5-S0 | S0-S0 |  X    |  |
|     | S2-S0  | S4-S0 | S6-S0 | S0-S0 |  X    |  |
| S6  |  X     |  X    | X     | X     | S0-S0 | X |
|     |  X     |  X    | X     | X     | S0-S0 | X |
|     | S0     | S1    | S2    | S3    | S4    | S5 |

Let's make some observations:
 - all cells where there is an `X` means that the corresponding states cannot be equal
 the first condition of state equivalency is not satisfied
 - as the two states cannot be equivalent in any way, all cells that require that two states 
 to be equivalent will be crossed out in the step 5.

> [!STEP]
> 5. Eliminate cells, until no more can be eliminated, based on: <br>
    - if the cell $(i,j)$contains a pair of states which one of them is in another eliminated cell we cross out also 
 the $(i,j)$ cell


|          |           |           |         |         |         |         |
| -------- | --------- | --------- | ------- | ------- |-------- | ------- |
| S1  |  X     |       |       |       |       |  |
|     |  X     |       |       |       |       |  |
| S2  |  X     | S3-S5 |       |       |       |  |
|     |  X     | S4-S6 |       |       |       |  |
| S3  |  X     |     X | X     |       |       |  |
|     |  X     |     X | X     |       |       |  |
| S4  |  X     |  X    | X     | X     |       |  |
| S4  |  X     |  X    | X     | X     |       |  |
| S5  |  X     |  X    | X     | S0-S0 |  X    |  |
|     |  X     |  X    | X     | S0-S0 |  X    |  |
| S6  |  X     |  X    | X     | X     | S0-S0 | X |
|     |  X     |  X    | X     | X     | S0-S0 | X |
|     | S0     | S1    | S2    | S3    | S4    | S5 |

as there is no more reduction possible we can draw the corresponding reduced
state transition table 

| Input Sequence | Current State  | Next State (`x=0`) | Next State (`x=1`) | Output (`x=0`) | Output (`x=1`) |
|---------------|--------------   |------------------|------------------|-------------|-------------|
| Reset         | S₀              | S`₁              | S`₁              | 0           | 0           |
| 0  or 1       | S`₁             | S`₃              | S`₄              | 0           | 0           |
| 00 or 10      | S`₃             | S₀              | S₀                | 0           | 0           |
| 01 or 11      | S`₄             | S₀              | S₀                | 1           | 0           |


