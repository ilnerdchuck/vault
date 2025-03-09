---
id: 1740841001-digital-signature
aliases:
  - Digital Signature
tags: []
title: Digital Signature
---

The digital signature is a mathematical scheme to allow actors to 
verify the [[1740839442-authentication|authenticity]] of digital messages and documents. It is based 
on [[1740842962-asymmetric-cryptography|asymmetric cryptography]], it requires a valid 
digital signature to give to the recipient proof that the message was 
created by a known sender ([[1740839442-authentication|authentication]]) and that 
message was not modified after the signature computation ([[1740838151-integrity|integrity]]) and [[1740839863-non-repudiation|non-repudiation]].
 The digital signature is a [[1740850972-message-authentication-code-mac|MAC]], but the hash value 
is encrypted with the private key of the person singing the data, so that 
the receiver can verify the authenticity of the message via the public key:
1. Alice computes $h = H(m)$ and $S = Enc(K_{PrivAlice},h)$
2. Alice sends $(m,s)$ to Bob
3. Bob computes $h = Dec(K_{PubAlice},s)$ and $h' = H(m)$
4. if:
    - $h == h'$ the signature is valid
    - $h \neq h'$ the signature is not valid
![digital_signature.png](assets/imgs/digital_signature.png)

# References
- [[1740851163-digital-certificate|DIgital Certificate]]
