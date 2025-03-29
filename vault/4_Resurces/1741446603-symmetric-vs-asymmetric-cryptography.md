---
id: 1741446603-symmetric-vs-asymmetric-cryptography
aliases:
  - Symmetric vs Asymmetric Cryptography
tags: []
title: Symmetric vs Asymmetric Cryptography
---

| Symmetric | Asymmetric |
| -------------- | --------------- |
| All involved actors share the same key  | it has two keys  |
| Key sharing is a big problem as whell as the number of keys | The $K_{Pub}$ key is usually packed in a [[1740851163-digital-certificate|Digital Certificate]] and released by a [[1741447065-certificate-authority-ca|Certificate Authority (CA)]]  |
| Does not grant mutual authentication and non-repudiation | Requires two keys for each involved actor |
| [[1740850107-advanced-encryption-standard-aes|(AES)]] is the most used algorithm | Grants mutual authentication and, if with a certificate, non-repudiation|
| Fast key and Dec/Enc execution | It hase larger keys, thus prevents brute force attacks |
| All | It is computationally heavy |

The conclusion is that there is no winner among the two:
 - Symmetric is used to provide fast encryption/decryption and **fast** key generation
 - Asymmetric is used to exchange the symmetric encryption keys

## Misconceptions
 - Asymmetric cryptography is more secure than Symmetric cryptography => **False** they are both 
 secure if the keys are long enough and handled in the correct way
 - Asymmetric cryptography has made symmetric cryptography obsolete => **False** Asymmetric cryptography is computationally 
 more expansive, it is only superior in cases of digital signatures
 - Key distribution is trivial for asymmetric cryptography, while the use of a key distribution center for symmetric
 cryptography is difficult => **False** Most of the time, managing key pairs is complex because it involves digital certificates. 
 Key management is always complex. 

# References
- [[1740842962-asymmetric-cryptography|Asymmetric Cryptography]]
- [[1740842949-symmetric-cryptography|Symmetric Cryptography]]

