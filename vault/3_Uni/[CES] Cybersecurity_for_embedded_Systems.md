---
id: "[CES] Cybersecurity_for_Embedded_Systems"
aliases: []
tags: []
title: "[CES] Cybersecurity for Embededd Systems"
---

### Sources 

 - [NIST](https://csrc.nist.gov/)
 - [drw0if cryptography notes](https://github.com/drw0if/Appunti)

Suggestes Textbooks:
 - Book Title

### Course info 
Professor: Alessando Savino
Email: [alessandro.savino@polito.it](mailto::alessandro.savino@polito.it)

Assistant: Nicola Scarano
email: [nicola.scarano@polito.it](mailto::nicola.scarano@polito.it)

At the end of the lectures there will be the labs
 - the lab will be dedicated to the projects

Exam Rules:
 - scores are valid indefinitely   
 - 2 parts:
    - Written exam 13 points
    - Project 19 points depending on the deadline 
    - Group projects of 3/4 people but also alone
    - topic somewhat related to the lectures 
    - send a mail to both professors with the students ids and 
    project choice
    - points split in 
        - project implementation 7 points
        - technical report 7 points
        - Oral presentation: 5-6 slides with the main topics  5 points
    - July and September no penalty 

# Cybersecurity Fundamentals

We can update the software meanwhile the hardware isn't upgradable.
Hardware can be as dangerous as software or even more => [[1740838202-hardware-vulnerabilities|Hardware Vulnerabilities]]

As hardware security engineers to design a secure hardware we need:
- Hardware implementation of encryption ([[1740862765-hardware-security-module-hsm|Hardware Security Module (HSM)]])
- Design locks or physical locks limiting access
- Devices to verify the user identities (Yubico?)
- Hiding signatures in the design files
- Intrusion detection
- Hardware boards limiting memory access
- Tamper resistant
- Policies an procedures

But implementing all of these (or some) adds overhead, size and power increases
while we try to keep them as low as possible in some environments. Since 
Security has begun to be an issue it has to be considered since the design phase.


- [[1740401439-in-order-execution|In Order Execution]]
- [[1740401450-out-of-order-execution|Out Of Order Execution]]

- [[1740838058-covert-channel|Covert Channel]]
- What does secure mean? => 
- [[1740838071-secure-boot|Secure Boot]] 
- [[1740838095-vulnerability|Vulnerability]]
- [[1740838102-threat|Threat]]
- [[1740838107-attack|Attack]]
- [[1740838118-confidentiality|Confidentiality]]
- [[1740838151-integrity|Integrity]]
- [[1740838161-availability|Availability]]
- [[1740838843-secret|Secret]]

# Introduction

- [[1740839246-cryptography|Cryptography]]
- [[1740839809-actor|Actor]]
- [[1740838118-confidentiality|Confidentiality]]
- [[1740838151-integrity|Integrity]]
- [[1740839442-authentication|Authentication (AuthN)]]
- [[1740839846-authorization|Authorization (AuthZ)]]
- [[1740839863-non-repudiation|Non-Repudiation]]
- [[1740841053-plaintext|Plaintext]]
- [[1740841067-ciphertext|Ciphertext]]
- [[1740841250-cryptographic-algorithm|Cryptographic algorithm]]
- [[1740841268-encryption|Encryption]]
- [[1740841280-decryption|Decryption]]
- [[1740841349-key-cs|Key (CS)]]
- [[1740850861-hash-function|Hash Function]]
- [[1740850532-plaintext-padding|Plaintext Padding]]
- [[1740850831-data-integrity|Data Integrity]]
- [[1741004467-random-number-generation|Random Number Generation]]
- [[1741451140-denial-of-service-dos|Denial Of Service (DoS)]]

## [[1740842949-symmetric-cryptography|Symmetric Cryptography]] 


### Cryptography Schemes
- [[1740859560-cryptographic-schemes|Cryptographic Schemes]]
- [[1740850315-stream-ciphers|Stream Ciphers]]
- [[1740850299-block-ciphers|Block Ciphers]]
#### Block Ciphers Usage Modes
- [[1740850150-electronic-code-book-ecb|Electronic Code Book (ECB)]]
- [[1740850212-cipher-block-chaining-cbc|Cipher Block Chaining (CBC)]] 
- [[1740859287-counter-mode-ctr|Counter Mode (CTR)]]
- [[1740850461-cipher-feedback-cfb|Cipher Feedback (CFB)]]
- [[1740850488-output-feedback-ofb|Output Feedback (OFB)]]

## SC algorithms 
- [[1740849391-data-encryption-standard-des|Data Encryption Standard (DES)]]
- [[1740850080-triple-des|Triple DES]]
- [[1740850107-advanced-encryption-standard-aes|Advanced Encryption Standard (AES)]]

## [[1740842962-asymmetric-cryptography|Asymmetric Cryptography]]

- [[1740850643-rsa-algorithm|RSA Algorithm]]
- [[1740850808-elliptic-curves-cryptosystem-ecc|Elliptic Curves Cryptosystem (ECC)]]
## Key Exchange
- [[1740850779-diffie-hellman|Diffie-Hellman]]

## [[1741446603-symmetric-vs-asymmetric-cryptography|Symmetric vs Asymmetric Cryptography]]

## Cryptographic Hash Algorithms
- [[1740850935-cryptographic-hash-algorithm|Cryptographic Hash Algorithm]]
- [[1740850999-message-integrity-code-mic|Message Integrity Code (MIC)]]
- [[1740850972-message-authentication-code-mac|Message Authentication Code (MAC)]]
- [[1740851019-message-identifier-mid|Message Identifier (MID)]]
- [[1740851073-key-digest|Key Digest]]

[[1740851163-digital-certificate|Digital Certificate]]
[[1740851189-chain-of-trust|Chain Of Trust]]

# Secure Coding

- [[1741608812-static-analyzer|Static Analyzer]]
- [[1741608820-linter|Linter]]

- [[1741608539-common-weakness-enumeration---cwe|Common Weakness Enumeration - CWE]]
- [[1741608558-common-vulnerabilities-and-exposures|Common Vulnerabilities and Exposures]]
## [[1741608632-memory-vulnerabilities|Memory Vulnerabilities]]

## Types of Vulnerabilities 
Issued by the MITRE
- [[1741610353-buffer-overflow-cwe-119|Buffer overflow CWE-119]] 
- [[1741625650-buffer-overhead-cwe---125|Buffer overhead CWE - 125]] 
- [[1741625668-use-after-free-cwe---416|Use After Free CWE - 416]]
- [[1741625688-integer-overflow-cwe---190|Integer overflow CWE - 190]] 
- [[1741686606-use-of-externally-controlled-formatted-string-cwe---134|Use of Externally Controlled Formatted String CWE - 134]]
- [[1741625751-os-command-injection-cwe---78|OS Command Injection CWE - 78]]
- [[1741625777-improper-imput-validation-cwe-20|Improper Imput Validation CWE-20]]
- [[1741688030-code-injection|Code Injection]]
- [[1741689680-code-reuse|Code Reuse]]
- [[1741690895-return-oriented-programming---rop|Return Oriented Programming - ROP]]
- [[1741691315-jump-oriented-programming---jop|Jump Oriented Programming - JOP]]
- [[1741691483-control-flow-integrity---cfi|Control Flow Integrity - CFI]]

----------

# Hardware Security
TODO: Catch up slide 40

# Topic 3


# Laboratories 
## Lab 1



