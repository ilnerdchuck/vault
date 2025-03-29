---
id: 1741454218-hash-functions
aliases:
  - Hash Functions
tags: []
title: Hash Functions
---

A hash function is any function that can be used to map data of arbitrary size to fixed-size values. The values returned by 
a hash function are called **hash values**, **hash codes**, **hash digests**, **digests**, or simply **hashes**. 
- take as input a block $M$ of variable length 
- generate a fixed length fingerprint $h=Hash(M)$

They are:
- Very fast to compute
- very difficult to invert knowing $h$
- They should be **collision-free**

# Use cases
- [[1741551206-key-derivation-function---kdf|Key Derivation Function - KDF]]
- **Signature Based Malware Detection**: The antivirus database contains signatures 
of known malware. The antivirus computes the hash of the analyzed files and 
compares it with the entries in the signature database 
- **Intrusion Detection System**: hash function are computed for each file. If an intruder modifies the file, the modification can be detected by recalculating the hash and comparing with the original one.
- **Version Control**: by using hash function to determine whether files on the server and local files are the same.
# References 
- [[1740850935-cryptographic-hash-algorithm|Cryptographic Hash Algorithm]]
- [[1740850972-message-authentication-code-mac|Message Authentication Code (MAC)]]



