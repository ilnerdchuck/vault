---
id: 1740850935-cryptographic-hash-algorithm
aliases:
  - Cryptographic Hash Algorithm
tags: []
title: Cryptographic Hash Algorithm
---

It is based on the [[1741454218-hash-functions|Hash Functions]], they **must** be:
- **One-Way function**: given $h=H(m)$, it is unfeasible to derive $m$ knowing only $h$ to find $x: H(x) = m$
- **Weak Collision Resistance**: given $h = H(m_1)$ and $m_1$, it is unfeasible to find $m_2\neq m_1$ such that $H(m_1) = H(m_2)$ => bound to a specific input $m_1$
- **Strong Collision Resistance**: it must be computationally unfeasible to find a pair of messages $m_1$ and $m_2$ such that
$H(m_1) = H(m_2)$ => it is bound to two arbitrary inputs

> [!DANGER]
> The length of the hash is inversely proportional to the length of the digest, if $n$ is the length of the digest 
> the **collision probability** is $\frac{1}{2^n}$

**Avalanche Effect** => They function such that a small change in the input drastically changes the output 
![crypt_hash.png](assets/imgs/crypt_hash.png)

## Algorithms
- MD2
- MD4
- MD5
- RIPEMD
- SHA-1
- SHA-2
- SHA-3

Hash algorithms are used usually in conjunction with encryption algorithms to grant [[1740838118-confidentiality|confidentiality]],[[1740838151-integrity|integrity]], [[1740839442-authentication|authentication]].

## Integrity 
The main use of hash functions is to guarantee the integrity of the message:
1. Alice sends to Bob $(m,H(m))$
2. Bob receives $(m,H(m))$ and computes $h' = H(m)$
3. if $h' == h$ then $m$ is the same for Alice and Bob
4. if $h' \neq h$ then $m$ is not the same for Alice and Bob

=> But this is vulnerable to [[1741447991-man-in-the-middle-mitm|Man-in-the-Middle (MITM)]] attacks. 

### Algorithms
- [[1740850999-message-integrity-code-mic|Message Integrity Code (MIC)]]: a normal hash computed to guarantee data integrity, 
but anyone can compute a hash knowing the algorithm 
- [[1740850972-message-authentication-code-mac|Message Authentication Code (MAC)]]: a hash computed considering also a
secret (Ex. A key). It can be computed only by actors knowing the secret, so it guarantees 
[[1740838151-integrity|integrity]] and [[1740839442-authentication|authentication]]
- [[1740851019-message-identifier-mid|Message Identifier (MID)]]: is a unique identifier that is added to the message to avoid [[1741456593-replay-attack|Replay Attack]]

# Encryption and hashes
As:
 - [[1740841268-encryption|Encryption]] gives data confidentiality.
 - Cryptographic hashes give us [[1740850831-data-integrity|data Integrity]] and [[1740839442-authentication|authentication]]

we can combine them to improve security by using two different keys: one to encrypt ($K_1$) and to 
compute the hash ($K_2$). Examples can be: 
 - **Authenticate and Encrypt - A&E** (SSH)
    - The output is $(Enc(K_1),MAC(K_2,m))$
    - Requires decryption before data integrity check
 - **Authenticate then encrypt -  AtE** (SSL, TLS)
    - The output is $Enc((K_1,m),MAC(K_2,m))$
    - Requires decryption before data integrity check and secure only with [[1740850212-cipher-block-chaining-cbc|CBC]] mode and [[1740850315-stream-ciphers|stream ciphers]]
 - **Encrypt then authenticate - EtA**
    - The output is $Enc((K_1,m),MAC(K_2,Enc(K_1,m)))$
    - **Data integrity can be checked without decrypting** 

But these examples are subject to vulnerabilities coming form the implementation, specific algorithms 
have been developed to formally combine [[1740838118-confidentiality|confidentiality]], [[1740850831-data-integrity|data Integrity]] and [[1740839442-authentication|authentication]]:
 - [[1741550580-ccm|CCM]] (Ex. used in ZigBee)
 - [[1741550601-eax|EAX]]
 - [[1741550611-gcm|GCM]]




