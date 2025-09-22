---
id: 1740850779-diffie-hellman
aliases:
  - Diffie-Hellman
tags: []
title: Diffie-Hellman
---

Nowdays it allows two users to securely share a secret on an untrusted channel.
The basic idea it that **two actors never share any common secret or any key pair** but use 
the DH algorithm to agree on a shared secret to be used as a symmetric key.  

1. Alice selects two public integers, $g$ and $p$, so that:
    - $1 < g < p$
    - $p$ is prime and very big
    - $g$ is a primitive root of $p$
2. Alice selects a secret a big random number $a$ and computes 
$$
    X = g^{a}\ mod\ p
$$
3. Bob selects a secret a big random number $b$ and computes 
$$
    Y = g^{b}\ mod\ p
$$
4. Alice and Bob exchange $X$ and $Y$
5. Alice computes 
$$
    K_A = Y^{a}\ mod\ p = g^{ab}\ mod\ p 
$$
6. Bob computes 
$$
    K_B = X^{b}\ mod\ p = g^{ab}\ mod\ p 
$$
7. Now Alice and Bob have the same $K_A = K_B$ without
sharing the $a$ and $b$ secrets.

![diffie_hellman_exchange.png](assets/imgs/diffie_hellman_exchange.png)
> [!DANGER] 
> It is subject to [[1741447991-man-in-the-middle-mitm|Man-in-the-Middle (MITM)]] attacks

Example of a MITM attack:
1. Alice selects a secret a big random number $a$ and computes 
$$
    X = g^{a}\ mod\ p
$$
2. Bob selects a secret a big random number $b$ and computes 
$$
    Y = g^{b}\ mod\ p
$$
3. Alice and Bob exchange $X$ and $Y$ but the attacker intercepts them 
4. Eve (the attacker) selects a secret a big random number $c$ and computes 
$$
    Z = g^{c}\ mod\ p
$$
and sends it to both Alice and Bob
5. Alice computes 
$$
    K_A = Z^{a}\ mod\ p = g^{ac}\ mod\ p 
$$
6. Bob computes 
$$
    K_B = Z^{b}\ mod\ p = g^{bc}\ mod\ p 
$$
7. Eve computes
$$
    K_{Ac} = X^{c}\ mod\ p = g^{ac}\ mod\ p 
    K_{Bc} = Y^{c}\ mod\ p = g^{bc}\ mod\ p 
$$
8. Now Alice and Bob are talking with Eve not directly with each other, and Eve can 
decrypt all the messages => they basically made a DH algorithm with Eve not with each other! ($K_A\neq K_B$)

The MITM attack can be mitigated with [[1740851163-digital-certificate|Digital Certificates]].









