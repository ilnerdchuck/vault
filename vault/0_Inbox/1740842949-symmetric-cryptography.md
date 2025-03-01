---
id: 1740842949-symmetric-cryptography
aliases:
  - Symmetric Cryptography
tags: []
title: Symmetric Cryptography
---

In Symmetric Cryptography (SC) the same [[1740841349-key-cs|key]] is used for [[1740841268-encryption|encryption]] and [[1740841280-decryption|decryption]].
![symmetric_key.png](assets/imgs/symmetric_key.png)

Defined by a message space $M$ and three algorithms:
- $Gen$: **key generation algorithm** outputs $k\in K$ in which $K$ is the set of all 
    possible keys of a given length. 
- $Enc$: **[[1740841268-encryption|encryption]] algorithm** takes a key $k$ and a plaintext $p \in  P$ as inputs
    and outputs a ciphertext $c = Enc(p,k)$
- $Dec$: **[[1740841280-decryption|decryption]] algorithm** takes the key $k$ and the ciphertext $c$
    as inputs and outputs the plaintext

> [!WARNING]
> for all $\fall (p,k)$ we have $Dec(Enc(p,k),k)=p$ 
> If this would not be true it means that to one ciphertext corresponds two plaintextes 
> ![Sym_msg.png](assets/imgs/Sym_msg.png)

They can be arranged on one of the available [[1740859560-cryptographic-schemes|Cryptographic Schemes]].

The key is exchanged between the [[1740843317-actors|actors]], sharing the key in a 
secure way is fundamental ([[1740843336-key-sharing|Key Sharing]]):
- [[1740843420-out-of-band-oob|Out-Of-Band (OOB)]]
- [[1740843452-key-agreement-algorithm|Key Agreement Algorithm]]
- [[1740843465-key-managment-system|Key Managment System]]
- [[1740842962-asymmetric-cryptography|Asymmetric Cryptography]] to exchange the key

otherwise we lose [[1740838118-confidentiality|confidentiality]]. 
Another issue of SC is the case of a lot of actors ($N$) the key quality the key management becomes 
unfeasible $nKeys= \frac{N(N-1)}{2}$.
![key_quantity.png](assets/imgs/key_quantity.png)

> [!DANGER]
> This does not take in account that after some time the keys have to be changed.
