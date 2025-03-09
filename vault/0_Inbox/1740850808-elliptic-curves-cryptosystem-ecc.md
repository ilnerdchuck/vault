---
id: 1740850808-elliptic-curves-cryptosystem-ecc
aliases:
  - Elliptic Curves Cryptosystem (ECC)
tags: []
title: Elliptic Curves Cryptosystem (ECC)
---

An alternative to [[1740850643-rsa-algorithm|RSA]] but with much shorter keys and increased security.
Used for encryption/decription, symmetric key sharing and digital signature.

Instead of working with modular arithmetic, ECC works on the surface described by a 2D 
elliptic curve. This makes the arithmetic much more complex. The computation change from 
factorization to logarithm on the 2D curve. But being more complex allows for 
much **shorter keys**.

# Algorithms
- [[1741453387-ec-dsa|EC-DSA]] for [[1740841001-digital-signature|digital signature]]
- [[1741453398-ec-dh|EC-DH]] for key managment
- [[1741453433-ec-mqv|EC-MQV]] for authenticated key agreement
- [[1741453461-ec-integrated-encryption-scheme-ecies|EC Integrated Encryption Scheme (ECIES)]]









