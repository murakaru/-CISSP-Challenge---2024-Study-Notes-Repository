
# Security Architecture and Engineering

With reference to the official guide, Domain 1 contains the below chapter and contents

- Chapter 1: Threat Modeling, Defense in Depth
- Chapter 7: Cryptographic systems and solutions, cryptanalytic attacks
- Chapter 8: Secure defaults, Fail securely, Keep it simple, Zero Trust, Privacy by design, Trust but verify, security models (e.g., Biba, Star Model, Bell-LaPadula), Select controls based upon systems security requirements, Understand security capabilities of Information Systems
- Chapter 9: Shared responsibility, Client-based systems, Server-based systems, Industrial Control Systems (ICS), Distributed systems, Internet of Things (IoT), Microservices, Containerization, Serverless, Embedded systems, High-Performance Computing (HPC) systems, Edge computing systems, Virtualized systems, 
- Chapter 10: Design site and facility security controls, Apply security principles to site and facility design
- Chapter 16: Least Privilege, Separation of duties (SoD), Cloud-based systems (e.g., Software as a Service (SaaS), Infrastructure as a Service (IaaS), Platform as a Service (PaaS))
- Chapter 20: Database systems




## Chapter 1: 
### Threat Modelling 

Identifying, Categorising and analysing potential threats.

Objective of Threat Modelling: To prioritize the potential threats against an organization's valuable assets.
- Proactive approach: during design and development.  It is a defensive approach to threat modelling: takes place during initial design. Based on predicting threats and designing specific defenses during the coding and crafting process.
- Reactive approach: once product is created and deployed. Takes care of the threats that could not be predicted during the design phase. It addresses unforeseen issues. This is known as thrat hunting or adversarial approach.

Microsoft SDLC goals in threat modelling 

- Reduce sec related design and coding defects 
- Reduce severity of remaining threats

Fuzz testing: dynamic testing technique that provides many different types of input to software to stress its limits and find previously undetected flaws


**Identifying threats**
How do we identify threats? 

- Focus on Assets: Determine the value of assets bafore identifying the threats 
- Focus on Attackers: Identify attackers and their motivations, goals, TTPs 
- Focus on Software: This is specific to comapanies that develops software. 

Guides/References for Threat Modelling 

1. STRIDE 
2. PASTA 
3. VAST

**Stride** 

![image](https://user-images.githubusercontent.com/19290577/216434624-314d2ad2-f616-4155-8e06-7e7f0ffc2d67.png)

**Pasta: Process of Attack, simulation and Threat Analysis**

7 stage threat modelling methoodology 
Risk centric approach

![image](https://user-images.githubusercontent.com/19290577/216446694-4138c814-4df3-48b2-8ce4-d112f7861d7f.png)

**VAST**

It integrates threat and risk management into an Agile programming environment on a scalable basis


**Risk Reduction**

Reduction analysis is also known as decomposing the application, system, or environment
Objective of risk reduction: Gain greater understanding of the logic of the product, its internal components, as well as its interactions with external elements. 

Concepts when decomposing the process 

- Trust Boundaries : Any location where the level of trust or security changes
- Dataflow Paths: The movement of data between locations
- Input Points: Locations where external input is received
- Privileged Operations: Any activity that requires greater privileges than of a standard user account or process, typically required to make system changes or alter security
- Details about Security Stance and Approach: The declaration of the security policy, security foundations, and security assumptions


Once threats are identified, they should be fully documented by defining the means, target, and consequences of a threat.

**Prioritization and Response**

After documentation, the next step is to rank or rate the threats. This can be accomplished using a wide range of techniques, such as Probability × Damage Potential ranking, high/medium/low rating, or the DREAD system.

The Disaster, Reproducibility, Exploitability, Affected Users, and Discoverability (DREAD)

- Damage Potential: How severe is the damage likely to be if the threat is realized?
- Reproducibility: How complicated is it for attackers to reproduce the exploit?
- Exploitability: How hard is it to perform the attack?
- Affected Users: How many users are likely to be affected by the attack (as a percentage)?
- Discoverability: How hard is it for an attacker to discover the weakness?


### Defence in depth 

Terms related to defense in depth:  Layering, levels, classifications, zones , realms , compartments , Silos , segmentations, lattice structure, and protection rings
Multiple contols in series - One after the other. 
Objective: No one control can protect against all threats 


## Chapter 7: PKI and Cryptographic Applications

asymmetric cryptosystems use pairs of public and private keys to facilitate secure communication without the overhead of complex key distribution systems.

*Common Asymetric cyptosystems today8

-- Rivest–Shamir–Adleman (RSA), 
-- Diffie–Hellman, 
-- ElGamal,
-- elliptic curve cryptography (ECC).

*public key cryptosystems*

each user is assigned a pair of keys: a public key and a private key.
The user make their public keys freely available to anyone with whom they want to communicate. - No weakness is introduced by this. 
The private key, is reserved for user - who owns the keys. private key should not be shared outside of key escrow and recovery arrangements.

The sender encrypts the plaintext message (P) with the recipient's public key to create the ciphertext message (C). When the recipient opens the ciphertext message, they decrypt it using their private key to view the original plaintext message.
Once the sender encrypts the message with the recipient's public key, no user (including the sender) can decrypt that message without knowing the recipient's private key (the second half of the public-private key pair used to generate the message).


Keys used within public key systems must be longer than those used in private key systems to produce cryptosystems of equivalent strengths.

Public key cyptography has high computational requirements 

**RSA**

3 creators: Ronald Rivest, Adi Shamir, and Leonard Adleman

*RSA Algorithm* 
- Choose two large prime numbers (approximately 200 digits each), labeled p and q.
- Compute the product of those two numbers: n = p * q.
- Select a number, e, that satisfies the following two requirements:
----- e is less than n.
----- e and (p – 1)(q – 1) are relatively prime—that is, the two numbers have no common factors other than 1.
- Find a number, d, such that ed = 1 mod ((p – 1)(q – 1)).
- Distribute e and n as the public key to all cryptosystem users. Keep d secret as the private key.


**key length**

- Symmettric: 128bits 
- RSA: 3.072 bits 
- Elliptic Curve: 256 bits 


**Elgamal**

Extended the Diffie-Hellman key exchange algorithm
Publised in 1985
Advantage: AT thge time of release, it was available to the public unlike RSA. 
Disadvantage: The algorithm doubles the size of any message that it encrypts hence a major hardship when encrypting large amounts of data that must be sent over a network.

**Elliptic Curve**
 Published in 1985
 Publishers: Neal Koblitz from the University of Washington and Victor Miller from IBM. 
 
 
 **Diffie - Hellman key exchange**
Allows two individuals to generate a shared secret key over an insecure communications channel.
Hence, they may use public key cryptography to generate a shared secret key that they then use to communicate with a symmetric encryption algorithm
This approach is known as hybrid cryptography
Uses Prime numbers, like RSA 
Its a key exchange protocol and not an encyption protocol. 
it is commonly used to create a shared secret key for use in Transport Layer Security (TLS), where it is referred to as either DHE or EDH

**Quantum Cryptography**

we can use principles of quantum mechanics to replace the binary 1 and 0 bits of digital computing with multidimensional quantum bits known as qubits.
quantum supremacy: the potential that quantum computers may be able to solve problems that are not possible to solve on contemporary computers.
it could render popular algorithms such as RSA and Diffie–Hellman insecure.


**Hash Functions**

*Purpose*: they take a potentially long message and generate a unique output value derived from the content of the message (Message digest). Message digests can be generated by the sender of a message and transmitted to the recipient along with the full message for two reasons.

- Integrity check. The recipient can use the same hash function to recompute the message digest from the full message. They can then compare the computed message digest to the transmitted one to ensure that the message sent by the originator is the same one received by the recipient.

- The message digest can be used to implement a digital signature algorithm.

Size of message digest: 128 bits or longer. The longer the message digest, the more reliable its verification of integrity.

*Requirements for a hash function*
- The input can be of any length.
- The output has a fixed length.
- The hash function is relatively easy to compute for any input.
- The hash function is one-way (meaning that it is extremely hard to determine the input when provided with the output). 
- The hash function is collision resistant (meaning that it is extremely hard to find two messages that produce the same hash value).


**SHA**

Secure Hash Algorithm
Successors: SHA-1, SHA-2, and SHA-3 
They are promoted by NIST 
They are specified in SHS (Secure Hash Standard) and FIPS (Federal Information Processing Standard) 

*SHA-1*
Input = Any length 
Output = 180 bit message digest
Processing of message = In 512 bit blocks, if message is not a multiple of 512, it pads the message.
Currently not supported since 2017. 

*SHA-2*
This has 4 variants 

- SHA-256:Output = 256 bit message digest using a 512-bit block size.
- SHA-224: uses a truncated version of the SHA-256 hash that drops 32 bits to produce a 224-bit message digest using a 512-bit block size.
- SHA-512: produces a 512-bit message digest using a 1,024-bit block size.
- SHA-384 uses a truncated version of the SHA-512 hash that drops 128 bits to produce a 384-bit digest using a 1,024-bit block size.

*SHA-3*
Keccak algorithm
Announcesd in 2015
it is slower than SHA-2, so SHA-3 is not commonly used outside of some specialized cases where the algorithm is efficiently implemented in hardware.

*MD5*
Creator: Ronald Rivest in 1991
It also processes 512-bit blocks of the message, but it uses four distinct rounds of computation to produce a digest of the same length as the MD2 and MD4 algorithms (128 bits).
Advantage: It is fast
Disadvantage: MD5 protocol is subject to collisions

*RipeMD*
an alternative to the SHA family that is used in some applications, such as Bitcoin cryptocurrency implementations

- RIPEMD produced a 128-bit digest and contained some structural flaws that rendered it insecure.
- RIPEMD-128 replaced RIPEMD, also producing a 128-bit digest, but it is also no longer considered secure.
- RIPEMD-160 is the replacement for RIPEMD-128 that remains secure today and is the most commonly used of the RIPEMD variants. It produces a 160-bit hash value.
 

Comparison of Hash Algorithm Value Lengths

HAVAL - 128,160,192,224,256
HMAC - Variable
MD5 - 128
SHA1 - 160
SHA2,224/SHA3,224 - 224
SHA2,256/SHA3,256 - 256
SHA2,384/SHA3,384 - 384
SHA2,512/SHA3,512 - 512
RIPEMD128 - 128
RIPEMD160 - 160
RIPEMD256 - 256
RIPEMD320 - 320

Digital Signatures 

What is a digital signature? How do we get it? 

Function: 
-Enforce non-repudiation to ensure that the message truly came from the sender. 
-Ensure integrity - that the message was not altered in transit(maliciously or accidentally)

Applications of Digital signatures 
- Authenticate code distributions and s/w patches

Generating a digital signature 
Digital signatures rely on Public key cryptography and hash algorithms 

Steps. 

Sender side
Run the message through a hashing algorithm to generate a message digest 
Run the message digest through an encryption algorithm (use senders private key) to generate a digital signature 
Attach the digital signature to the message and send to recipient 

Receiver side
Run the digital signature through a decryption algorithm (use senders public key) 
Run the message through a hashing algorithm ro generate a message digest. 
The receiver compares the message digest received with the generated digest. If they match, integrity is maintained. If not,the message was altered in transit. 

How do we provide confidentiality with digital signatures? 
Lets look at the same case above 

Sender side
Run the message through a hashing algorithm to generate a message digest 
Run the message digest through an encryption algorithm (use senders private key) to generate a digital signature 
Attach the digital signature to the message 
Run the message and digital signature through an encryption algorithm (using the receivers public key) 

Receiver side
Use the receivers private key to decrypt the message. 
Run the digital signature through a decryption algorithm (use senders public key) 
Run the message through a hashing algorithm ro generate a message digest. 
The receiver compares the message digest received with the generated digest. If they match, integrity is maintained. If not,the message was altered in transit. 

Adding the few steps above ensures confidentiality as the entire message is encryped before transmission. 
Encrrpted using receivers public key and decryped using the receivers private key. 


HMAC 
This stands for Hashing Message Authentication Code 
It implements partial digital signatures to ensure integrity during transmission 
However, this does not provide non repudiation. 

Which key should you use?
When you want to encrypt a confidential message? Use the receivers public key 
When you want to decrypt a confidential message? Use the receivers private key 
When you want to digitally sign a message you are sending? Use the senders private key 
When verifying the signature on a message received? Use the senders public key 

HMAC combines with other hashing algoriths such as MD5, SHA2, SHA3 using a shared secret key. 
Where would one apply HMAC? Where symettric keys are used. It serves as a middleground between encrypted message digest algorithm and computationally expensive digital signatures based on PKI 

Digital Signature Standard
This is a document that specifies federally approved digital signature algorithms. 
This standard specifies approved encyption algorithms 
1. DSA - Digital Signature Algorithm specifies in FIPs 186-4
2. RSA algorithm
3. ECDSA - Elliptic Curve DSA

### Public key Infrastructure 
This provides hybrid cryptography.
It combines symmetric ans asymmetric encryption, hashing algorithms and digital signatures. 
This enables communication between previous unknown parties. 

Components of PKI 
1. Digital certificates
2. Certificate Authorities

Digital Certificates 
This is assurance that people we are communicating with are who they say they are. 
A digital certificate os a verifies public key 
They are governed under x.509 standard

Contents of a digital signature
1. The version of x.509
2. Serial number
3. Signature Algorithm identifier (the technique used by CA to sign the contents of the certificate
4. Issuer name (The CA that issued the certificate)
5. Validity period
6. Subjects name (Common Name and distinguihed name of the entity owning the public key)
7. The subjects public key

What does a wildcard mean? 
It indicates that the certificate is good for subdomains as well. 

Certificate Authorities 
Thisis the glue of the PKI 
It is a notarization service for Digital signatures 
Examples of CAs: Symantec, AWS, digicert. 


### Cryptographic systems and solutions

### cryptanalytic attacks

