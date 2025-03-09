---
id: 1740927090-pipelined-processor
aliases:
  - Pipelined Processor
tags: []
---

# Pipelined Processor
![pipeline_processor.png](assets/imgs/pipeline_processor.png)
- Pipeline breaks => Stalls
    - Cache Miss
    - Hazards
        - Structural => Depends on resources
        ![structural_hazard.png](assets/imgs/structural_hazard.png)
        - Data
        ![data_hazard.png](assets/imgs/data_hazard.png)
        Solved trough
            - Forwarding
            - Out Of Order Execution
            - Register Renaming: RAW, WAR, WAW
        - Control
        ![control_hazard.png](assets/imgs/control_hazard.png)
            - Jump: Instruction Queue
            - Branch:
                - Delayed Branching
                - Branch Prediction
                    - Static
                    - Dynamic: 1 bit, 2 bit, Branch History Table (BHT)
(Pipeline improvements) Superscalar 
- Parallel Execution
- Limited Execution
- Dependency check expansive
- Very Long Instruction Word (VLIW) 
    - Compiler performs Dependency Checking
    - Increased Code Size
    - lack of binary compatibility 
- Explicitly Parallel Instruction Computing (EPIC)
    - Dynamic VLIW
    - 128 bit word with 3 instruction in 41 bits and 5 bit with info on parallelism 
