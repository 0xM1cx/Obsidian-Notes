**Cryptology** is the science of secure communication, it is the science for researching and designing cryptographic algorithms to ensure security in the digital space. It is based on encryption and decryption. . Cryptology science is a very broad science and is divided into 2 itself: "Cryptography" and "Cryptanalysis".

## Cryptography
“**Cryptography**” is the whole of the techniques used to transform the transmitted information into a form that cannot be understood by unauthorized people. Cryptography includes mathematical methods that try to provide the basic objectives of information security such as confidentiality, integrity, authentication, and non-repudiation.
![[basics3.png]]

## Cryptanalysis
“**Cryptanalysis**” is a branch of cryptology that examines the security of crypto algorithms in order to decrypt the encrypted data and tries to find their weaknesses. “Cryptanalysis” tries to detect mathematical vulnerabilities in the crypto algorithm in order to convert ciphertext to plaintext. In other words, it aims to break cryptographic algorithms.


## Objectives of Cryptography
Cryptography serves some purposes, as in every branch of science. Cryptography has tasks to meet the needs that arise over time. 4 principles, which are among the principles of information security, are also valid for cryptography:  
  
- [[#Confidentiality]]
- [[#Integrity]]
- [[#Authentication]]
- [[#Non-repudiation]]

### Confidentiality
Data/information sent over communication devices should not be understood by unauthorized people. Malicious people should not be able to make sense of the data, even if they obtain information that should remain between the parties.
### Integrity
The “Integrity” principle, one of the information security principles, tells us that in such a case we have to verify that the data is not cryptographically compromised. While designing algorithms in cryptography, algorithm design should be done by considering data integrity.
### Non-repudiation


### Authentication


## What is Encoding/Decoding?

“**Encoding**” is often confused with encryption as a concept. In fact, the two terms are used for very different purposes. *Encoding* is the process of converting data into a specific character set form. Unlike encryption algorithms, it is a conversion algorithm that is used without using key values ​​and without security concerns. There is also the opposite of the encoding process. For example, one of the most frequently used encoding algorithms is the "base64" algorithm. “Decoding” is the opposite of encoding algorithms. The encoded data with the decoding process will turn into previous data.
![[basics8.png]]

## Types of Cryptography
- [[#Symmetric Ciphers]]
- [[#Asymmetric Ciphers]]
- [[#Protocols]]
### Symmetric Ciphers
**Symmetric encryption** algorithms are cryptographic algorithms that use the same key in encryption and decryption operations. DES, 3DES, and AES crypto algorithms can be given as examples of symmetric encryption algorithms.
- DES(Data Encryption Standard)
- 3DES(Triple DES)
- AES (Advanced Encryption Standard)
- Blowfish
- Twofish
- RC4 (Rivest Cipher 4)
- IDEA (International Data Encryption Algorithm)
- Serpent
- Camellia
- CAST-128
### Asymmetric Ciphers
An entirely different type of cryptosystem was introduced in 1976 by *Whitfield Diffie*, *Martin Hellman*, and *Ralph Merkle*. In this type of cryptosystem, which is introduced as "**Public-key cryptography**" or "**asymmetric cryptography**", two different keys are used instead of a single key. While “public key” is used for encryption, “secret key” or in other words “private key” is used for decryption. An example of an asymmetric crypto algorithm is the RSA (Rivest–Shamir–Adleman) algorithm.
![[types2.png]]
- RSA (Rivest-Shamir-Adleman)
- DSA (Digital Signature Algorithm)
- ECC (Elliptic Curve Cryptography)
- ElGamal
- Diffie-Hellman
- Merkle-Damgård construction (used in hash functions, not an encryption algorithm by itself)
- McEliece
- NTRUEncrypt
- Lattice-based cryptography algorithms (e.g., NTRU)
- Post-Quantum Cryptography algorithms (e.g., code-based, hash-based, lattice-based, multivariate polynomial, etc.)
### Protocols
Cryptographic protocols deal with the implementation of cryptographic algorithms. Symmetric and asymmetric crypto algorithms are used in the security infrastructure of many software. An example of the protocols in which these algorithms are applied is the "Transport Layer Security (TLS)" protocol. In this type of cryptographic protocol, symmetric and asymmetric crypto algorithms are generally used together. This is called “Hybrid Schemes”. The reason for using both types of algorithms is that each has its strengths and weaknesses.



## Random Number Generator
In cryptography, there are many criteria for the algorithm to be secure. One of these criteria is related to the randomness of key generation. For a crypto algorithm to be strong in cryptography, it is important that the key is long enough and random.

Three types of Random Number Generator:
- [[#True Random Number Generators(TRNG)]]
- [[#Pseudorandom Number Generators(PRNG)]]
- [[#Cryptographically Secure Pseudorandom Number Generators(CSPRNG)]]
### True Random Number Generators(TRNG)
- This is a method that generates random numbers based on real physical operations. An example of this type of random number generation is a coin flip or a dice toss. 
- Although it is an effective method in terms of randomness, it is not a preferred method in terms of applicability and speed. 
### Pseudorandom Number Generators(PRNG)
- This method needs an initial random value to ensure randomness. This value is called **Seed**. This value can come from the TRNG method. It generates random numbers step by step according to some mathematical calculations over this first value. By applying the same mathematical calculations recursively, a number is generated at each step.
- Compared to the TRNG method, its application in practice is much easier and faster. But it is not secure and unpredictable enough for use in cryptography. Because if the first value is determined, it is not possible to talk about completely random values, since the value calculated in each step will be the same every time.
### Cryptographically Secure Pseudorandom Number Generators(CSPRNG)
- This is an unpredictable variant of PRNG. As in this method, it is not possible to predict and calculate the next value(0 or 1 bit) to be produced mathematically. 
- This method frequently used in software testing, but CSPRNG is a cryptography specific method.

## Base64 Encoding/Decoding
“Base32” and “Base64” are methods of representing binary data with a specific character set based on “ASCII”. In other words, it is a data representation method.

**ASCII (American Standard Code for Information Interchange):** ASCII format is a table that emerged in the name of digital systems having a common numerical value between characters. In this way, the binary equivalent of a character is the same in all electronic systems.

> Attackers use the "Base32" encoding method for data exfiltration with the DNS protocol. It often indicates an abnormal situation when SOC analysts see data transmitted in "Base32" format, especially in queries related to DNS requests.

