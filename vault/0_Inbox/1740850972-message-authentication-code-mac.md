---
id: 1740850972-message-authentication-code-mac
aliases:
  - Message Authentication Code (MAC)
tags: []
title: Message Authentication Code (MAC)
---

The MAC guarantees [[1740838151-integrity|integrity]] and [[1740839442-authentication|authentication]].
It needs a shared secret between the actors, then: 
1. Alice computes $h = H(m)$ and $c = Enc(k,h)$
2. Alice sends to bob $(m,c)$
3. Bob receives $(m,c)$ an computes $h = Dec(k,c)$
4. Bob computes $h' = H(m)$
5. If:
    - $h' == h$ then $m$ is the same for Alice and Bob, since the hash is the same and involves the usage of a shared secret, [[1740850831-data-integrity|data Integrity]] and [[1740839442-authentication|authentication]] are granted.
    - $h' \neq h$ then someone tempered with the message ([[1740850831-data-integrity|data Integrity]]) or the ciphertext ([[1740839442-authentication|authentication]]), Bob can not distinguish between the two.

# Key Digest
A **Key Digest** is a MAC that does not require encryption thus more efficient, there is still a shared 
secret between Alice and Bob:
1. Alice computes $h = H(m,k)$
2. Alice sends to bob $(m,h)$
3. Bob receives $(m,h)$ an computes $h' = H(m,k)$
4. If:
    - $h' == h$ then $m$ is the same for Alice and Bob, since the hash is the same and involves the usage of a shared secret, [[1740850831-data-integrity|data Integrity]] and [[1740839442-authentication|authentication]] are granted.
    - $h' \neq h$ then someone tempered with the message ([[1740850831-data-integrity|data Integrity]]) or the ciphertext ([[1740839442-authentication|authentication]]), Bob can not distinguish between the two.
## KD problems
Implementing a keyed digest may lead to specific vulnerabilities that compromise [[1740850831-data-integrity|data integrity]] and [[1740839442-authentication|authentication]]. The solution is to use standardized key digest:
 - [[1741549905-hmac|HMAC]]: Uses a cryptographic hash function and a secret key to generate the MAC.
 - [[1741549950-cbc-mac|CBC-MAC]]: Uses a block cipher in [[1740850212-cipher-block-chaining-cbc|CBC]] mode and a secret key to generate the MAC



