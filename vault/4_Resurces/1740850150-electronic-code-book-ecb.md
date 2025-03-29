---
id: 1740850150-electronic-code-book-ecb
aliases:
  - Electronic Code Book (ECB)
tags: []
title: Electronic Code Book (ECB)
---

In this [[1740850299-block-ciphers|block cipher]] arrangement the [[plaintext]] 
size is divided by the block input size and each 
block is [[1740841268-encryption|encrypted]]/[[1740841280-decryption|decrypted]] 
independently form the others 

![ECB_cipher.png](assets/imgs/ECB_cipher.png)

> [!DANGER]
> ECB leads to information leakage: it is subject to plain text attacks 
