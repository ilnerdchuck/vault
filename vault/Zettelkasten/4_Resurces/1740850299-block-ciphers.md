---
id: 1740850299-block-ciphers
aliases:
  - Block Ciphers
tags: []
title: Block Ciphers
---

In block ciphers the [[1740841053-plaintext|plaintext]] and [[1740841067-ciphertext|ciphertext]] are 
processed by stages, each stage takes an $n$ bit input and 
produce a $n$ bit output, the most simple block takes a plaintext and a key as input and 
produce a ciphertext as output.
> [!CHECK]
> It operates on a fixed number of bits

> [!WARNING]
> For the reversion to be possible each block must produce a unique ciphertext block.
![block_cipher.png](assets/imgs/block_cipher.png)

If more blocks are used some sctructures can be used:
- [[1740850212-cipher-block-chaining-cbc|Cipher Block Chaining (CBC)]]
- [[1740859287-counter-mode-ctr|Counter Mode (CTR)]]
- [[1740850150-electronic-code-book-ecb|Electronic Code Book (ECB)]]
- [[1740850488-output-feedback-ofb|Output Feedback (OFB)]]

> [!INFO]
> They work really whell in parallel archuitectures

# References
- [[1740850107-advanced-encryption-standard-aes|Advanced Encryption Standard (AES)]] (CBC or ECB mode)
- [[1740849391-data-encryption-standard-des|Data Encryption Standard (DES)]]
- [[1740850080-triple-des|Triple DES]]
