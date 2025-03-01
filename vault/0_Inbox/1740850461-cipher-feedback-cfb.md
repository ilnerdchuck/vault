---
id: 1740850461-cipher-feedback-cfb
aliases:
  - Cipher Feedback (CFB)
tags: []
title: Cipher Feedback (CFB)
---

In this [[1740850299-block-ciphers|block cipher]] arrangement. It converts
a the block cipher in a [[1740850315-stream-ciphers|stream cipher]].
The blocks are managed in a similar way to [[1740850212-cipher-block-chaining-cbc|CBC]],

- In the [[1740841268-encryption|encryption]] phase
    - First block has as input an [[1740871240-initialization-vector|Initialization Vector]] 
    - the ciphertext is the XOR of the current output and the 
    relative block plaintext
    - Every block input is the previous ciphertext 

> [!DANGER]
> The encryption can't be parallelized!
> At each stage i need to wait for the previous block to finish the calculations

![CFB_encryption.png](assets/imgs/CFB_encryption.png)

- In the [[1740841280-decryption|decryption]] phase
    - First block has as input an [[1740871240-initialization-vector|Initialization Vector]] 
    - the palintext is the XOR of the current output and the 
    relative block ciphertext
    - Every block input is the previous ciphertext 
> [!CHECK] GOOD 
> The decryption can be parallelized!
> To compute the current block i need only the input to the previous block 
![CFB_decryption.png](assets/imgs/CFB_decryption.png)
