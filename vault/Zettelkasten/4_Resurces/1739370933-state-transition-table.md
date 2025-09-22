---
id: 1739370933-state-transition-table
aliases:
  - state transition table
tags:
  - Digital Design
---
[[1739365679-state-diagram|State Diagram]]

# State Transition Table

A state strnsition table is able to show how the state of a [[1739371932-finate-state-machine|FSM]] evolves based on the current state and current inputs. 
It consists of a [[1739372212-truth-table|truth table]] in which the inputs are the current state 
and the inputs of the FSM, the outputs of the truth table are the 
next state along with the new FSM outputs.

There are multiple variations of the table: Input (I), State (S), Output (O)
- One-Dimension:
    the row is composed of: Inputs , Current State, Next State and optionally
    the output associated with the transition.
    
    | Inputs | Current state | Next state | Output |
    |--------|-------------- |------------|--------|
    | I₁     | S₁            | Sᵢ         | Oₓ     |
    | I₂     | S₁            | Sⱼ         | Oᵧ     |
    | ...    | ...           | ...        | ...    |
    | Iₙ     | S₁            | Sₖ         | O𝓏     |
    They are as close as they can to a truth table.
    
- Two-Dimensions:
    They are two dimensional tables that can be arranged in two ways
    
    1. one dimension is the current state and the other the inputs, 
    the row-column intersection indicates the next state and optionally 
    the output associated with the transition.
     
    | Current state \ Input  | I₁     | I₂      | ...  | Iₙ     |
    |----------             |--------|------   |------|--------|
    | **S₁**                | Sᵢ/Oₓ  | Sⱼ/Oᵧ   | ...  | Sₖ/O𝓏  |
    | **S₂**                | Sᵢ′/Oₓ′| Sⱼ′/Oᵧ′ | ...  | Sₖ′/O𝓏′|
    | **...**               | ...    | ...     | ...  | ...    |
    | **Sₘ**                | Sᵢ″/Oₓ″| Sⱼ″/Oᵧ″ | ...  | Sₖ″/O𝓏″|
    
    2. one dimension is the current state and the other one is 
    the next state, meanwhile the intersection are the inputs 
    and optionally the outputs associated to the transition. 

    | Current state \ Next state | S₁      | S₂      | ...  | Sₘ     |
    |--------------              |-------- |-------- |------|--------|
    | **S₁**                     | Iᵢ/Oₓ   | —       | ...  | —      |
    | **S₂**                     | —       | —       | ...  | Iⱼ/Oᵧ  |
    | **...**                    | ...     | ...     | ...  | ...    |
    | **Sₘ**                     | —       | Iₖ/O𝓏   | ...  | —      |

- n-Dimentional
    
