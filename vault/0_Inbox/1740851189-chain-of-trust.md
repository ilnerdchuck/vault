---
id: 1740851189-chain-of-trust
aliases:
  - Chain Of Trust
tags: []
title: Chain Of Trust
---

A chain of thrust is a chain that connects all certificates starting from a final one 
through intermediate CA to arrive at the root CA. A root CA is a company or organization 
capable of creating self-signed certificates. Intermediate CAs they sell certificates but 
can not sign it's own certificate, they need an higher CA authority in the chain to sign it.

![chain_of_thrust.png](assets/imgs/chain_of_thrust.png)
