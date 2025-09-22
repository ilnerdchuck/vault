---
id: 1741625688-integer-overflow-cwe---190
aliases:
  - Integer overflow CWE - 190
tags: []
title: Integer overflow CWE - 190
---
[CWE-190](https://cwe.mitre.org/data/definitions/190.html)

# Issue
An integer overflow occurs when a variable is incremented to a value that can not be contained in the 
current variable type/size of memory, this leads to: 
 - The variable changes drastically value without control 
 - Unexpected Behaviour 
 - Data Corruption
 - System Crash

Integer overflow can be exploited to alter the execution flow of a program, determine the offset of 
memory locations and determine the size of the memory locations. 

> [!IMPORTANT]
> It is not related to any programming language it is only implementation dependent

It impacts [[1740838161-availability|availability]], [[1740838151-integrity|integrity]] and 
[[1740838118-confidentiality|confidentiality]]

## Examples 
to add:

# Solution
- Use specific libraries written to avoid this weakness (SafeInt c++)
- Perform input validation

