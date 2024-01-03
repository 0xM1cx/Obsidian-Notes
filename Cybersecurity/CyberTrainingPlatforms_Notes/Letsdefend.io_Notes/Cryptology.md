**Cryptology** is the science of secure communication, it is the science for researching and designing cryptographic algorithms to ensure security in the digital space. It is based on encryption and decryption. . Cryptology science is a very broad science and is divided into 2 itself: "Cryptography" and "Cryptanalysis".

## Cryptography
“**Cryptography**” is the whole of the techniques used to transform the transmitted information into a form that cannot be understood by unauthorized people. Cryptography includes mathematical methods that try to provide the basic objectives of information security such as confidentiality, integrity, authentication, and non-repudiation.
![[basics3.png]]

## Cryptanalysis
“**Cryptanalysis**” is a branch of cryptology that examines the security of crypto algorithms in order to decrypt the encrypted data and tries to find their weaknesses. “Cryptanalysis” tries to detect mathematical vulnerabilities in the crypto algorithm in order to convert ciphertext to plaintext. In other words, it aims to break cryptographic algorithms.

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