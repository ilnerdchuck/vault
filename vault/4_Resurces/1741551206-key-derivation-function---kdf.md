---
id: 1741551206-key-derivation-function---kdf
aliases:
  - Key Derivation Function - KDF
tags: []
title: Key Derivation Function - KDF
---

Hash can be used to derive cryptographic keys, a cryptographic key shuld be 
**perfectly random**=> this is not entirely possible in software. Keys are sometimes 
derived form passwords, which are not that random:
$$
    K = KDF(P,S,N) 
$$
 - $P$ is the password or passphrase
 - $S$ is a seed or salt, used to make $P$ more random
 - $N$ is the number of iteration to be done with the hash function
Example is the **PBKDF2** or to store the access password of users. 

