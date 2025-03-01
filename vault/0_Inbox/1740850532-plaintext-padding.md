---
id: 1740850532-plaintext-padding
aliases:
  - Plaintext Padding
tags: []
title: Plaintext Padding
---

If the block size ([[1740850299-block-ciphers|Block Ciphers]]) is grater than the [[1740841053-plaintext|plaintext]], 
bits are added to the plaintext itself to accomoddate for the lack of.

The possible padding bits are:
 - **Zero Padding**: add null bits `0000 | p`, but this requires more information about the padding
 - **Random Padding**: add random bytes `0x07 0x02 | p`
 - PKCS#5, PKCS#7, SSL, TLS: the value of each byte of padding is equal to the lenght of the pagging itself \
 Ex if $n_{bytes}Padding = 5$ => `0x05 0x05 0x05 0x05 0x05 | p `

















