---
id: 1740841250-cryptographic-algorithm
aliases:
  - Cryptographic algorithm
tags: []
title: Cryptographic algorithm
---

An algorithm that transforms a [[1740841053-plaintext|plaintext]] ($m$) into a [[1740841067-ciphertext|ciphertext]] ($c$) usually using a [[1740841349-key-cs|key (CS)]] (k).

The forward execution of the algorithm plaintext + key => ciphertext is called 
[[1740841268-encryption|encryption]] ($C$). 
$$
    c = C(m,k)
$$
The reverse execution of the algorithm 
ciphertext +k => plaintext is called [[1740841280-decryption|decryption]] ($D$).
$$
    m = D(c,k)
$$

Usually $C$ and $D$ are the same algorithm and the symbol used is $C$ for both encryption and decryption.

