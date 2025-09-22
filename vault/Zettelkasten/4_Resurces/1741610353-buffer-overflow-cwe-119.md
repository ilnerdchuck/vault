---
id: 1741610353-buffer-overflow-cwe-119
aliases:
  - Buffer overflow CWE-119
tags: []
title: Buffer overflow CWE-119
---

# Issue
The software performs a read or a write operation on a memory buffer of a given size, but the software 
but the software reads or writes outside the memory buffer.
## Cause
The programing language allows direct addressing of memory locations and does not automatically ensure that these 
locations are inside the memory buffer that is used leading to:
 - Memory Corruption
 - Execution of arbitrary code
 - Control Flow Alteration
 - Stealing of Sensitive Information
 - Unexpected Behaviour
 - System Crash

It impacts [[1740838151-integrity|integrity]], [[1740838161-availability|availability]] and [[1740838118-confidentiality|confidentiality]]

## Code snippets

strcopy dosent check for null arrays and the size is the same or if there is a terminator char 

# Examples
- Heartbleed in TLS
