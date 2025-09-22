---
id: 1740849391-data-encryption-standard-des
aliases:
  - Data Encryption Standard (DES)
tags: []
title: Data Encryption Standard (DES)
---

The DES algorithm is a [[1740842949-symmetric-cryptography|symmetric key]] algorithm based on 56bit keys 
and S-boxes[^1] which are [[1740863690-look-up-tables-lut|Look Up Tables (LUT)]] that implement 
a non linear function which apply two permutations and one transposition
to the input. The actual size of the key is 64 bit but 8 bits are used for parity   

It applies two crucial properties:
- Diffusion: Every character of the ciphertext depends on **every** character of the 
    plaintext
- Confusion: combines the plaintext and key in a hard manner, this doesn't allow 
    the ciphertext to be simply reversible an separated in the plaintext and key. 
![DES_diagram.png](assets/imgs/DES_diagram.png)
a more detailed diagram is
![DES_graph_details.png](assets/imgs/DES_graph_details.png)
where 
- $P$: Permutation
- $EP$: Expansion
- $S$: S-Box
- $CT$: throws some bit of the key and trows it away


> [!DANGER] Vulnerabilities
> It is insecure as it uses a relatively small 56bit key size.([[1740862422-brute-force-attack|Brute Force Attack]])
 

[^1]:![sbox.png](assets/imgs/sbox.png)

 
