---
id: 1740850315-stream-ciphers
aliases:
  - Stream Ciphers
tags: []
title: Stream Ciphers
---

In Stream ciphers [[1740841053-plaintext|plaintext]] and [[1740841067-ciphertext|ciphertext]] are 
processed 1byte/bit at a time without considering blocks ([[1740850299-block-ciphers|Block Ciphers]])
The encryption of each digit is dependent on the current state of the cipher, 
usually they operate on bits and the operation is the XOR.
To guarantee it's robustness it's critical that the next value of the stream is **not** 
predictable knowing it's previous portions.
It is important that the usage of the key in each plaintext exchange is almost single use 
otherwise, for example if the operation is the XOR, it could be simply reversed => 
the two [[1740843317-actors|actors]] need to share the same key generator.

![Stream_ciphers.png](assets/imgs/Stream_ciphers.png)

# References
- [[1740850107-advanced-encryption-standard-aes|Advanced Encryption Standard (AES)]] (CTR, CFB, OFB mode)
- [[1740861022-one-time-pad-otp|One Time Pad (OTP)]]
