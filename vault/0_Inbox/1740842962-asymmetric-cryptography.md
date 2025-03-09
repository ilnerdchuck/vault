---
id: 1740842962-asymmetric-cryptography
aliases:
  - Asymmetric Cryptography
tags: []
title: Asymmetric Cryptography
---

Asymmetric cryptography is based on key pairs:
 - A [[1741428254-public-key|Public Key]] ($K_{Pub}$) to which any actor has access
 - A [[1741428262-private-key|Private Key]] ($K_{Priv}$) to which only the owner of the 
 key pair has access

The keys are usually very long to be computationally unfeasible.

> [!TIP]The keys and encryption methods are generated to have a specific function:
> If the plaintext is encrypted with one of the keys the other one must be able to 
> decrypt it. 
> $$
>    Dec(K_{Pub}, Enc(K_{Priv},P)) = P \\ 
>    Dec(K_{Priv}, Enc(K_{Pub},P)) = P \\ 
>    Dec(K_{Priv}, Enc(K_{Priv},P)) \neq P \\ 
>    Dec(K_{Pub}, Enc(K_{Pub},P)) \neq P \\ 
>$$

 A key pair belongs to a single actor.
> [!DANGER]
> It is computationally heavier compared to symmetric cryptography 
> and vulnerable to quantum analysis 


It is mostly used to exchange symmetric keys or for actor authentication 
or [[1740839863-non-repudiation|non-repudiability]] 

They can be used to:
- Perform symmetric key distribution: **[[1740838118-confidentiality|confidentiality]]** 
    - The sender encrypts the symmetric key using as asymmetric algorithm with the 
    **recipient's public key**, $K_{Pub}$ and sends the ciphertext
    - The recipient decrypts the ciphertext using the same asymmetric algorithm and his 
    **private key**, $K_{Priv}$  
    ![key_distribution.png](assets/imgs/key_distribution.png)
- [[1740841001-digital-signature|Digital Signature]]: it requires [[1740838151-integrity|integrity]] 
and [[1740839442-authentication|authentication]]
    - Alice generates a signature by encrypting a message (usually a 
    [[1740850935-cryptographic-hash-algorithm|Cryptographic Hash]] of the message)  with **her private key**
    - Bob verifies the signature by decrypting the ciphertext using **Alice public key**
    if he succeed it means that only Alice can have generated that ciphertext   
    ![digital_signature.png](assets/imgs/digital_signature.png)

## Most Used asymmetric algorithms
- [[1740850643-rsa-algorithm|RSA Algorithm]]
- [[1740850808-elliptic-curves-cryptosystem-ecc|Elliptic Curves Cryptosystem (ECC)]]
- [[1740850779-diffie-hellman|Diffie-Hellman (DH)]]
- [[1741444490-digital-signature-algorithm-dsa|Digital Signature Algorithm (DSA)]]

![asym_alg_comparison.png](assets/imgs/asym_alg_comparison.png)

# References
 - [[1740841001-digital-signature|Digital Signature]]
 - [[1741428594-secure-sockets-layer-ssl|Secure Sockets Layer (SSL)]]
 - [[1741428617-transport-layer-security-tls|Transport Layer Security (TLS)]]
 - [[1741428637-https|HTTPS]]
