---
id: 1740850107-advanced-encryption-standard-aes
aliases:
  - Advanced Encryption Standard (AES)
tags: []
title: Advanced Encryption Standard (AES)
---

It is a [[1740842949-symmetric-cryptography|Symmetric key]] [[1740850299-block-ciphers|block cipher]].
It can use different key sizes: 128,192,256 bit. 
The main phases of the algorithm are:
- Substitution bytes
- Shift rows
- Mix Columns
- Add **round key** 

As the [[1740849391-data-encryption-standard-des|(DES)]] algorithm AES uses the 
S-boxes but the funciton that generates them is know 

it can implemented with one of the available [[1740850299-block-ciphers|block ciphers]] arrangments: 
- [[1740850150-electronic-code-book-ecb|Electronic Code Book (ECB)]]
- [[1740850212-cipher-block-chaining-cbc|Cipher Block Chaining (CBC)]] 
- [[1740859287-counter-mode-ctr|Counter Mode (CTR)]]
- [[1740850461-cipher-feedback-cfb|Cipher Feedback (CFB)]]
- [[1740850488-output-feedback-ofb|Output Feedback (OFB)]]

