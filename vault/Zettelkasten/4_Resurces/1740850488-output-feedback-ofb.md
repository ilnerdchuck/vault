---
id: 1740850488-output-feedback-ofb
aliases:
  - Output Feedback (OFB)
tags: []
title: Output Feedback (OFB)
---

In this [[1740850299-block-ciphers|block cipher]] arrangement. It converts
a the block cipher in a [[1740850315-stream-ciphers|stream cipher]].
The blocks are managed in a similar way to [[1740850212-cipher-block-chaining-cbc|CBC]]

- In the [[1740841268-encryption|encryption]] phase
    - First block has as input an [[1740871240-initialization-vector|Initialization Vector]] 
    - the ciphertext is the XOR of the current output and the 
    relative block plaintext
    - Every block input is the previous encryption block output 

> [!DANGER]
> The encryption can't be parallelized!
> At each stage i need to wait for the previous block to finish the calculations
![OFB_encryption.png](assets/imgs/OFB_encryption.png)

- In the [[1740841280-decryption|decryption]] phase
    - First block has as input an [[1740871240-initialization-vector|Initialization Vector]] 
    - the palintext is the XOR of the current output and the 
    relative block ciphertext
    - Every block input is the previous decryption block output 
> [!DANGER]
> The decryption can't be parallelized!
> At each stage i need to wait for the previous block to finish the calculations

![OFB_decrypt.png](assets/imgs/OFB_decrypt.png)
