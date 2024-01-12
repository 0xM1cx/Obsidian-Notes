```toc
```
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

## Uses and Features
**Base32** and **Base64** is an encoding method that allows sending text-based data to systems that process binary data type. In this encoding method, all data can be kept without data loss. It is an effective method to avoid some characters that may cause problems in the target system.

The numbers 32 and 64 indicate the total number of characters in the character set. For example, the character set in the base64 encoding method includes both lowercase and uppercase letters and numbers. The character set of base32 encoding method does not include lowercase letters and some numbers. 

- **Base64 character set:** 26 lowercase + 26 uppercase + 10 digits + “/” sign + “+” sign = 64 characters 
- **Base32 character set:** 26 uppercase letters + 6 digits = 32 characters
![[Pasted image 20240109225446.png]]![[Pasted image 20240109225505.png]]

### Base64 Encoding Logic
Below is the step-by-step base64 encoding, explained in detail with an example:  
#### Step 1

First, the data to be given to the base64 encoding algorithm is selected. A text has been chosen for clarity: “base64”  

#### Step 2
Since bit-based operations will be done, "base64" text is converted to binary:  
**Binary:** 01100010 01100001 01110011 01100101 00110110 00110100  

The following address can be used for this process:  
**Online Converter:** https://www.asciitohex.com/  

#### Step 3

Data converted to binary format is divided into 6-bits, respectively:  

![](https://letsdefend.io/images/training/cryptography/8.Base64%20EncodingDecoding/base3.png)
#### Step 4

Each bit sequence separated as 6-bit is found in the base64 encoding table, and the characters are ordered consecutively:  

![](https://letsdefend.io/images/training/cryptography/8.Base64%20EncodingDecoding/base4.png)
![](https://letsdefend.io/images/training/cryptography/8.Base64%20EncodingDecoding/base5.png) 
**Encoded Data** = YMFzZTY0

## Hash Functions
- Hash functions are a special type of function that performs certain operations mathematically and in computer science, which operates on bits. Hash functions are not encryption/decryption algorithms. Therefore, the hash function does not need a key to perform operations.
- The length of the input can be variable while the length of the hash is fixed length
- The reliability of the hash function depends on producing different hashes for different inputs. For example, if two different inputs cause the same hash, as in the image below, the hash function loses its reliability. The situation where two different inputs produce the same hash is called "**collision**".
![[Pasted image 20240112093017.png]]

### Purpose of using hash
- The hash produced as a result of the hash function can be used as the digital identity of the data. For example, hash values are used to distinguish malware. You get information about malware when you query the hash of the malware in known large-scale malware archive 
- Hash function can be used for integrity check. If a problem has occurred in the transmission of the data or file and there has been a change in the bits of the file/data, hashes are used to understand this. 
- Passwords are kept in the form of hashes on windows and linux systems. Hash functions are unidirectional. Being one-way means that the input given to the hash function cannot be obtained over the hash. I.e, you cannot decode the hash

## Digital Signatures
A digital signature is a cryptographic feature that allows verifying who sent and signed data in the digital environment. The requirements of the "Non-repudiation" principle included in the previous topics in the training are fulfilled with a digital signature.

In the Windows operating system, files with the extension "exe" have a digital signature. Thanks to this signature, it is possible to see which company or who signed the file and verify it.

In digital signing algorithms, 2 different keys are used for signing and signature verification: “public key” and “private key”. A private key is a personal key used in signing. The reason why this key is used in the signing process and kept secret is that it can be signed on behalf of the owner of the key. The public key, on the other hand, is used to verify signatures that are shared publicly and signed with a private key.

![[Pasted image 20240112102728.png]]

## SSL/TLS Protocol
The SSL/TLS protocol is a protocol designed for secure two-party communication in computer networks. SSL/TLS protocol is a protocol that is frequently used in e-mail, instant messaging, web applications and VoIP applications. It ensures that the communication between the parties remains confidential. The SSL/TLS protocol has 3 main purposes:  
  
- **Encryption:** It allows to hide data from parties other than the 2 communicating parties.
- **Authentication:** It allows to verify that both parties that want to provide secure communication are the correct parties.
- **Integrity:** It ensures that the outgoing data has not been changed between the 2 parties with which secure communication is provided.
![[ssl2.png]]

The SSL/TLS protocol uses certificates. Certificates are important to ensure secure communication. It is actually SSL/TLS certificates that enable encrypted traffic to occur by using HTTPS instead of HTTP on the browser.

SSL/TLS certificate is a data file on the server. The client uses the server's certificate to verify the identity of the server and to get the public key from the server to be used in communication with the server.

The browser uses its own list of certificate authorities to verify certificates. If the certificate of the connected server does not belong to a trusted certificate authority, the browser considers it insecure and warns the user.
![[ssl6.png]]

### How does SSL/TLS Principle Work?
1. The user send a request to the server
2. The server sends it public key to the user along with its own SSL/TLS certificate.
3. The user's browser checks and verifies whether the sent certificate is valid.
4. The user's browser generates a randomly generated symmetric key and encrypts this symmetric key with the public key sent by the server and sends it to the server.
5. The server decrypts the encrypted symmetric key with the private key and the symmetric key is sent to the server in a secure manner.
6. From this stage onwards, the server encrypts every data to be sent to the user's browser using this symmetric key.
7. Since the user has this symmetric key, he decrypts the incoming encrypted data with the symmetric key and displays the page securely. 
![[ssl7.png]]

## Cryptographic Attacks
Cryptanalysis is a branch of science that falls under cryptology. Those interested in this branch of science test the reliability of crypto algorithms designed by cryptography experts.

By discovering attack methods specific to the Crypto algorithm, the weakness in the algorithm is exploited and the reliability of the crypto algorithm is tested in this way. Cryptanalysis is basically examined under 3 headings:  
- [[#Classical Cryptanalysis]]
- [[#Implementation Attacks]]
- [[#Social Engineering]]
![[attack1.png]]

### Classical Cryptanalysis
Classical cryptanalysis tries to obtain the plaintext from the ciphertext or to obtain the key from the ciphertext. Simple methods are used when finding the weakness of the crypto algorithm. Structural weaknesses of the Crypto algorithm can be used or all possibilities can be tried with brute-force techniques. 
#### Brute-force attacks

### Implementation Attacks
### Social Engineering