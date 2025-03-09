---
id: 1740850643-rsa-algorithm
aliases:
  - RSA Algorithm
tags: []
title: RSA Algorithm
---

It is the most used [[1740842949-symmetric-cryptography|symmetric]] algorithm. Suitable for encryption/decryption, 
symmetric key sharing and digital signature.

## Key generation
To generate a pair of (K_{Pub},K_{Priv}):
1. Choose two big prime numbers as secret $P$ and $Q$
2. Compute $n = P \times Q$
3. Compute $\varphi = (P-1)(Q-1)$
4. Choose an exponent $e$ such that: $1 < e < \varphi$
5. Compute the private exponent: $ d = e^{-1} mod\ \varphi$
6. $K_{Pub} = {e,n}$
7. $K_{Priv} = {d,n}$
9. $P$ and $Q$ are deleted after the generation ends

## Encryption
Given $K_{Pub} = {e,n}$ and $K_{Priv} = {d,n}$ to encrypt a message $m$ the sender has to compute 
$$
    c = Enc(m,K_{Pub}) = m^e mod\ n
$$

## Decryption
Given $K_{Pub} = {e,n}$ and $K_{Priv} = {d,n}$ to decrypt a ciphertext $c$ the receiver has to compute 
$$
    m = Enc(c,K_{Priv}) = c^d mod\ n 
$$

> [!DANGER]
> In the $Enc/Dec$ functions the exponential is used and it's calculation is expansive



# Security
## Factorization Problem 
The length of the public key is important but we need to keep in mind where it is stored in our system, a cache can be very 
valuable but we might have issue with the cache policies so is a nogo, the attacker might force the replacement of the memory location where the key is stored thus leaking pieces of the key itself.
The key step of the RSA algorithm is to determine two prime numbers $P$ and $Q$ that are used to compute $n = P \times Q$. 
The factorization problem consist in finding $P$ and $Q$ knowing only $n$. 

## Attacks
The algorithm is based on the exponentiation of integers and modulo operator (very large integers 
are required for good resistance), the key to break the algorithm is to find a suitable way to factoring large numbers.

- Brute force attack: to find $K_{Priv}$ Eve has to find $P$ and $Q$ by factoring $n$. Thus $P$ and $Q$ must be big 
enough so that $n(P\times Q)$ is hard to factorize.
- Small Private Exponent ($d$): the smaller $d$, the faster the decryption. If $d$ is small => $e$ is necessarily large.
A public key with a large $e$ is a good hint for the attackers, $d$ can be found more easily.
- Small Public Exponent ($e$): if $e$ is small exploiting $m^e  mod\ n$ is simpler.
- $P$ and $Q$ are close in value: $n = P \times Q$ => if $P \approx Q$ then $n \approx 2P or\ 2Q$ and can be 
efficiently factored using [[1741451691-fermat-factorization|Fermat Factorization]].




