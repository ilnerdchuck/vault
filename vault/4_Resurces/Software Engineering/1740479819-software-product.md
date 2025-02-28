---
id: 1740479819-software-product
aliases:
  - Software Product
tags: []
title: Software Product
---

Software products are the result of a [[1740479851-software--process|Software  Process]], it is an 
application with documentation that can be delivered to the end user. 

The quality of the end product depends on the quality of the process
    
## Product Properties

- **Functional Properties** : Do something (verb + nouns)=> described in the [[1740494161-product-requirements-document-prd|PRD]] and 
developed in the design phase.
- **Non Functional Properties**  (modifiers of the functional properties):  
    - Efficiency
        - Given a function the response time should be within a margin
        - Given a function/for a complete product:
            - How much memory
            - How much CPU
            - How much bandwidth 
            - How much Energy
            - Etc ...
    - Usability: User interaction, how easy is for a user to interact and learn the product: 
        - Effort needed to learn the product 
        - Satisfaction expressed by the user
        - Existence of functions needed by the user => Requirement of the client respected
        - How easy is to deploy the product
    - Correctness: Having zero [[1740494770-defects|defects]], allowing the product to provide the functionality in all cases
        - To test correctness you need to test all inputs to check the expected outputs, but it is 
            impossible to to that => too many cases.
    - Reliability: 
        - how many visible [[1740494770-defects|defects]] i can allow for an amount of time expressed with a percentage or number
        - Often the time to fix the defects is calculated and given to the user 
        Ex. 
    - Availability: 
        - How much time a part of the product is/is not available to the end user  
    - Security:
        - Prevent malicious access or grant only authorized access to a resource
    - Safety:
        - Towards the end user:  
            - High safety: absence of hazardous situations 
            - low safety: presence of hazardous situations
        - we need to analyze and avoid the hazardous situations 
    - Dependability: 
        - Security + Safety + Reliability
        - Measures how much the system/application/product can be trusted and do what i advertise for
    - Maintainability: 
        - how easy is to modify (effort in time) to modify a function 
        - how easy is to deploy on a different platform

Example:
![traffic_light_functionalities.png](assets/imgs/traffic_light_functionalities.png)
Yellow arrows are non functional properties meanwhile the blue ones are Functional proprieties. 
Non functional properties adds basically constraints derived from one of the fields.

Both functional and non functional properties should be defined before starting the development  
and verified before the deployment 
