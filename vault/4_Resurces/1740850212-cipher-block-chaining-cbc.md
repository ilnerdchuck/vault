---
id: 1740850212-cipher-block-chaining-cbc
aliases:
  - Cipher Block Chaining (CBC)
tags: []
title: Cipher Block Chaining (CBC)
---

In this [[1740850299-block-ciphers|block cipher]] arrangement the [[plaintext]] is split 
into blocks each one to the size of the available [[1740841268-encryption|encryption]]
algorithm (Ex 128 bit for [[1740850107-advanced-encryption-standard-aes|(AES)]]). 
The blocks are not independent from each other:
- In the encryption phase the input of each block is the relative 
plaintex portion XORed with the previous block ciphertext
    - the first block ciphertext is an [[1740871240-initialization-vector|Initialization Vector]]
> [!DANGER]
> The encryption can't be parallelized!
> At each stage i need to wait for the previous block to finish the calculations
> $Enc(k,p_i\bigoplus c_{i-1})$

![CBC_encryption.png](assets/imgs/CBC_encryption.png)
- In the encryption phase the plaintext of each block is given by 
    XORing the previous block ciphertext input with the current block 
    plaintext output
     - the first block ciphertext is the same [[1740871240-initialization-vector|initialization vector]]
     as the encryption
> [!CHECK] GOOD 
> The decryption can be parallelized!
> To compute the current block i need only the input to the previous block 

![CBC_decryption.png](assets/imgs/CBC_decryption.png)

