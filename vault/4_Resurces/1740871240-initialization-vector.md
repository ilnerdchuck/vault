---
id: 1740871240-initialization-vector
aliases:
  - Initialization Vector
tags: []
title: Initialization Vector
---

> [!DANGER]
> The initialization vector must me shared between the [[1740843317-actors|actors]] and must be 
> changed every encryption operation. The risk could be information leakage: if two
> plaintexts are equal they will produce the same ciphertext with the same key and same IV.
