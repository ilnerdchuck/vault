---
id: 1740859287-counter-mode-ctr
aliases:
  - Counter Mode (CTR)
  - Galois Mode (GM)
tags: []
title: Counter Mode (CTR)
---


In this [[1740850299-block-ciphers|block cipher]] arrangement. It converts 
a the block cipher in a [[1740850315-stream-ciphers|stream cipher]].
It is based on [[1740870484-nonce|nonces]], the nonce i concatenated 
with a coutner wich total size is equal to the block size, 
and the counter value is increm,ented by 1 for each data block.

In the [[1740841268-encryption|encryption]] phase
 - The nonce+counter in encrypted with the key and then XORed qith the corrisponding 
 block plaintext.
> [!DANGER]
> The encryption can't be parallelized!
> At each stage i need to wait for the previous block to finish the calculations

![CTR_encryption.png](assets/imgs/CTR_encryption.png)

In the [[1740841280-decryption|decryption]] phase 
 - The nonce+counter in encrypted with the key and then XORed qith the corrisponding
 block ciphertext.
![CTR_decryption.png](assets/imgs/CTR_decryption.png)

> [!CHECK] GOOD
> Both decryption and encryption can be parallelized: the counter value can be precomputed


