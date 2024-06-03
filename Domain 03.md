
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
- Reactive approach: once product is created and deployed. Takes care of the threats that could not be predicted during the design phase. It addresses unforeseen issues. This is known as threat hunting or adversarial approach.

Microsoft SDLC goals in threat modelling 

- Reduce sec related design and coding defects 
- Reduce severity of remaining threats

Fuzz testing: dynamic testing technique that provides many different types of input to software to stress its limits and find previously undetected flaws


**Identifying threats**
How do we identify threats? 

- Focus on Assets: Determine the value of assets before identifying the threats 
- Focus on Attackers: Identify attackers and their motivations, goals, TTPs. 
- Focus on Software: This is specific to companies that develops software. 

Guides/References for Threat Modelling 

1. STRIDE 
2. PASTA 
3. VAST

**Stride** 

![image](https://user-images.githubusercontent.com/19290577/216434624-314d2ad2-f616-4155-8e06-7e7f0ffc2d67.png)

**Pasta: Process of Attack, simulation and Threat Analysis**

7 stage threat modelling methodology 
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
The glue that binds PKI 
It is a notarization service for Digital signatures 
Examples of CAs: Symantec, AWS, digicert. 

What is a Registration Authority?  These assist CA with the burden of veryfying identity before issuing digital certificates. This allows the CAs to remotely validate the useridentity 

How do CAs protect their own private keys? 
Using an offline CA to protect their root certificate. This is isolated from the network. The offline CA is used to creat subordinate online CAs used to issue certificates. 

What is certificate chaining? 
The use of a series of internediate CAs. The browser checks the certificate chain to verify the identity of intermediate CA and traces back to the root CA. 

Can you have an Internal CA? 
Yes. Multiple organisations have their own implementation of CAs internally. These certs are self signed. Internal systems must be configured to trust these self signed certificates. 

Cert Lifecycle 

1. Create/enroll
2. Validate
3. Revoke

Creation
1. Approach a CA with documents for enrollment
2. Provide your public key to the CA. This is in the form of a cert signing request (CSR)
3. CA creats an x.509 cert with identifying information  and copy of digital certs
4. You are now free to circulate the cert.

Types of certificates 
Domain velidation certificate 
Extended validation 

Verification 
What do you check when you receive a digital certificate 
1. CA digital signature
2. Validity period
3. Ensure the cert was not revoked (CRL or OCSP)
4. The cert contains the data you are trusting

What is certificate pinning? 
This instructs the browsers to attacj a cert to a subject for an extended period of time. When sites use cert pinning, the browser associates that site with their public key which allows users or admins to notice anf intervene if certificate unexpetedly changes 

Revocation
What are the reasons for revocation?
1.The cert was compormised 
2.The cert was erroneously issued
3.Details on the cert changes e.g subjects name 
4.The security association changed. 

Revocation request grace period: Max time a CA will perform requested revocation

Techniques to verify authenticity of certs 
1. CRL
2. OCSP
3. Certificate Stapling

Certificate Formats 
The formats can be either in binary or text format 

1. Distingushed Encoding Rule (DER)- Binary - der,.crt,.cer
2. Privacy Enhanced Mail (PEM) - Text - .pem, .crt
3. Personal Information Exchange (PFX) -Binary - .pfx,.p12
4. p7B - Text -.p7b

   
### Hybrid Cryptography
 = Symettric + Asymmetric 
 Why do we need it? To exchange the ephemeral key using asymettric encryption. The data is exchanged using symettric algorithm
 Example: TLS

 ### Applied Cryptography 
 Portable devices : Disk encyption e.g bitlocker, Encrypting File System(EFS) , FileVaule encryption
 Email: For confidentiality, encrypt. For integrity, hash. For authentication, integrity and nonrepudiation, digitally sign. For confidentiality, Integrity, origin authentication , encrypt and digitally sign 
 PGP:Combines CA and Web of trust
 S/MIME - Secure MultiPurpose Internet Mail xtensions. Used by MS, Apple and google.Relies on x.509 certificates
 
 ## Web Applications - The use of SSL and TLS. 
  SSL -insecure for use today
  TLS - Secure communication. How? Relies on exchange of digital certs to negotiate the encrption/decryption parameters. Uses both symmetric and asymmetric encryption.
  Explaining TLS
  - When a user accesses the website, it retrieves the servers cert and extracts the servers public key
  - Browser creates a random symmetric key using its own private key. The 2 systems use this key for all future communication.
  - The server decrypts the symettric key using its own private key. 


Tor and Dark Web - tor was known as the onion router. 
Stenography and Watermarking. Stenography is the art of using crypographic techniques to embed secret messages within another message. 

## Networking 
circuit Encryption - To protect data in motion. Link encrption(To protect the communication circuit) and end to end encyption(protects the communication between two parties e.g client and server. 
IPSEC - It relies on AH and ESP. AH ensures integrity and nonrepudiation. ESP provides confidentiality and integrity 
 Modes of IPSEC operation: 
  Transport mode - for end to end encryption- ony the payload is encrypted 
  Tunnel Mode - Entire packet including the header is encypted. 
 Operation: At runtime, a security association is established. This records status and configuration of connection. Its simplex. For two way connection, 2 SAs are needed. If you want bidirectional channel using both AH and ESP, you will need to set up 4 SAs.

 ### Applications 
 1. Blockchain
 2. Lightweight cryptography
 3. Homomorphic Encryption

### Cryptographic Attacks 

Analytic attack 
Implementation attack 
Statistical Attack 
Brute Force attack 
Fault Injection attack 
Side-Channel Attack 
Timing attack 
Frequency analysis and ciphertext-Only attack 
Known Plaintext attack 
Chosen Plaintext 
Chosen Ciphertext 
Meet in the middle 
Man in the middle


### Chapter 8: 

## Secure Design Principles 

### Objects and Subjects 
Subject? the active element that makes a request for a resource e.f user,process
Object? This is the resource being accessed. A file, printer e.t.c

Relationship between object and subject: Writing, reading, deleting, printing, copying , moving, backing up e.t c

Transitive Trust: If A trusts B , and B trusts C, then A can trsut C. 
Transitive trust is a serious security concern as it might cause bypassing of controls. 

Closed and open systems 
Closed: Same manufacturere, deigned to work in  a silo
Opne: Based upon agreed upon standards, can be integrated, APIs 

### Secure Defaults 
"The tyranny of the defaults"
Defaults are not particularly secure. Most manufacturere incorporate default settings to make the first time usage of the products less cumbersome.
What ius secure defaults? SD3+C - Where security products are digned with the emost secure settings enabled by default.

### fail Securely 
To fail securely, design to ancipate and defend against errors. Error handling mechanisms e.g try..catch, conditional statements(if ..then), Input sanitization, input filtering or input validation. This prioritises the physical security of the assets. This is a synonym to fail closed

#### fail soft: 
To allow a system to continue operation after component failure.
#### fail safe:
This proritises the human aspect . When a failure occurs the system fails in a manner that prioritises the health and safety of people. 

#### Fail open
This protects the availability of a system incase it fails. Protects people. 
#### Fail close
This protects the integrity and confidentiality of the system. Protects Assests

Summary: 
Fail open ensures availability of the systems during system failure.
Fail Safe, Fail closed and Fail secure ensure Confidentiality and Integrity during system failure.
Fail open and fail safe aims to protects people during system failure 
Fail closed and fail secure aims to protect assets during system failure. 

### Keep it simple

What is KISS? A recommendation to build systems that are less complicated.

Concepts of KISS
- DRY (Do Repeat Yourself) - Imperative for change management. Makes it less difficult to change. 
- Computing minimalism - code should use the least necesary hardware and software.
- Rule of Least power - use the least powerful programming language.
- Worse if better - Quality of SW does not increase with the increase in capabilities and functions. Few dunctions in code are more secure. 
- You arent going to need it - Do not add functionalities if not needed.
  
### Zero Trust 

- Nothing is automatically trusted.
- Concept of never trust, always verify
- This is build around the concept of assuming breach - always assume that a security breach has occurred.
- Every access request must be authenticated, authorised and encryped before access of granted.
- Zero Trust relies on internal microsegmentation and adherence to principles of least priviledge.
- These principles prevent lateral movement so that in the event of a breach, the ability to move laterally is impedded.
- How do we implement zero trust? there is a wide range of solutions to implement zero trust
   1. Internal segmentation Firewalls(ISFWs)
   2. MFA
   3. IAM
   4. NG endpoint security
 Zero trust is formalised in NIST SP 800-207

### Privacy by design
Integrates privacy design concepts during the design phase. Focus is prevention rather than remedy.
Same concept as secure by design
- Proactive and not reactive
- Privacy by default
- privacy in design
- end to end security
- Visibility and transparency
- Respect for user privacy

### Trust but Verify 
The traditional approach of trusting subjects and devices within the companies sec perimeter. This increases vulnerability. 
It is no longer sufficient in the meodern world due to the changing threat landscape. 

## Techniques for ensuring CIA 

1. Confinement - Used to restrict actions of a program.
   Process confinement allows a process to read from and write to only certain memory locations.
   This is sandboxing.
   The goal is prevent data leakage.
   Confinement can be implemented in the Operating system itself or service.
   
2. Bounds - These are the limits within which it can access memory and resources.
   The areas within which a process is confined or contained.
   Physical bounds are more secure but very expensive.
    
3. Isolation - Depends on confinement and bounds.
   This ensures that any behaviour will affect the memory and resources associated with that process.
   This protects the OS environment and kernel. Prevents an application from accessing the memory and resources of other applications.
   
4. Access Controls - Only allows authorised subjects to access objects.
   Options for Access conteols - discretionary, role-base and mandatory.
   
6. Trust and Assurance - Trust is the presence of security mechanisms
   Assuarance is the degree of confidence (How reliable the system is). Assurance must be established on individual systems.
   If there is a change on a system, an assessment needs to be conducted based on   real world usage of the system with an aim to guarantee assurance.

## Security Models 

- Trusted Computing base
  Combination of H/W, S/W and controls that work together. It is the only portion of the system that can be trusted to adhere and enforce security policies.
    Sec Perimeter: Logical boundary separating the TCB from the rest of the system to ensure that there is no inseure comm between TCB and other elements of the computer system.Trusted paths are used to communicate between TCB and other parts of the system.
    Ref Monitors - This sits between every subject and object. Collection of components in the TCB that work together to impelement the ref monitor is the sec kernel. The sec kernel will mediate all the requests that match the access rules for the system.
  
- State Machine Model
  This describes a system that is always secure no matter the state its in.
  What is a state? This is a snapshot of the system at a specific point in time. When there is a transition(moment an input is translated into an output) then the state changes. A secure machine will always boot into a secure state
  
- Information Flow Model
  This focuses on information  flow.
  This prevents unauthorised, insecure flows between systems (diff levels of systems.
  Information flow model allows all tge authorised flows while preventing unauthorsied flows
  
- Noninterference model: Based on the impact that a subject with a higher security level affects the system state of actions of a subject with a lower security level.
  The actions of higher sec level subject should not affect the lower sec level subject.
  If this is not observed, it might lead to information leakage and create covert channels. 

- Take-grant model: This dictates how rights can be passed form one subject to another or from subject to object.
  There are four rules in the take-grant model
  Take rule: Allows a subject to take rights over an object
  Grant rule: Allows a subject to grant rights to an object
  Create rule: Allows a subject to create new rights
  Remove rule: Allows a subject to remove rights it has.  
  
- Access Control model: A table of subjects and objects thet indicates the actions the eash subject can perform. 
- Bell Lapadula Model: Born in the 70s. Focus on Confidentiality.
  A subject with any level of clearance can access all the objects at or below their clearance level.
  However, for their clearance level, access is compartmentalised and rights issued on a need to know basis.

  Build on state machine model concept
  - Simple security Property - No read up
  - The Star Security property - No write down
  - The dicretionary security property - System uses an access matrix to enforce discretionaty access control.
 
    Not supported today for file sharing and networking
    
- Biba Model: Focuses on Integrity 
  Designed after bell la padula
  Build on the state machine concept.
  Based on the information flow and is a multilevel model.
  - Simple integrity property - no read down
  - Star - No write up.
 
   So why no read down? For integrity. You do not want unvalidated data to read validated documents due to potentoial data contamination.
  Biba is designed to
  1. Prevent object modifivation bu unauthorised subjects
  2. Prevent unauthorised modification of objects by authorised subjects
  3. Protect internal and external objects consistency.
 
  A classification level is required for the Biba Model.
  
  Disadvantages of Biba
  
 - Only addresses integrity - not confidentiality of Availability
 - Focus on protectong assets from external threats, assumming that internal threats are handled programmatically.
 - Does not address access control management.
 - Does not prevent copvert channels. 
  
- Clark -Wilson Model

 Focuses on data Integrity 
 Does not rely on the state machine concept 
 It defines a data item and allows modfication through an interface(a program or application)
 An object can only be accessed through a program or interface 

 Items defined under this model 
 1. CDI : Constrained Data Item - A data item whose integrity is protected by the security model
 2. UDI: Inconstrained Data Item - A data item that is not constrained by the security model. Data that is not validated would be considered unconstrained.
 3. IVP: Integrity Verification Procedure - A procedure that scans data items and confirms their integrity.
 4. TPs - Transformation Procedures - These are the only procedures allowed to modify a CCDI.

This model used security labels to grant access to objects 

 
- Brewer and Nash Model: This was created to allow access control to change dynamically based on the users activity. (A kind of state machine concept)
  Defines the security domains that are potentially in conflict and prevents a subject with access to one domain that belongs to a specific conflic class from accessing any other domain that belongs to the same conflict class.
  This used the prociple of data isolation.
  Called the chinese wall model/ethicall wall/cone of silence
  
- Goguen Meseguer model:  An integrity model
  Foundation of the non interference model
  Based on determining a set or domain that a subject can access.
  Subjects are only allowed to perform operations on predetermined objects
  When similar users are grouoed into a domain, the members of one subject domain cannot interfere with the members of another subject domain
  
- Sutherland Model: An integrity model
  Based on the state machine concept and the information flow model.
  This model focuses on defining a set of syetsm states, intitial states and transitions.
  Through the use of predetermined states, integrity of maintained and interference is prohibited.
  
- Graham-Denning model: Focus on secure creation and deletion od subjects and objects
    It is a cobination of

  - Securely creating an object
  - Securely create a subject
  - Securely delete an object
  - Securely delete an object
  - securely provide read access right
  - Securely provide grant access right
  - Securely provide the delete access right
  - Securely provide the delete grant access
  - Securely provide the transfer access right
 
    It uses an access control matric to specify permissions
    
- Harrison-Ruzzo-Ullman model:Focus on assignment of object access rights to subjects as well as the resilience of those assigned rights. Its an extention of Graham-Denning model.
  A set of procedures to edit/alter access rights of a subject over an object.
  There are also integrity rules e.g
   .Inorder to create, add a subject of object to the matrix, it must not already exist
   .In order to remove a subject or object from a mtrix, it must already exist
   .If several commands are performed at once, they must all be successfull, else, none of the commands will be executed.


  ### Selecting Controls based in system Sec requirements

  #### Common Criteria
  #### Authorisation to Operate

  ### Understand security Capabilities of Information Systems

  #### Memory Protection
  #### Virtualisation
  #### Trsued Platform Module
  #### Interfaces
  #### Fault Tolerance
  Ability for the system to suffer a fault but continue operating. How?Using RAID array, employing additional servers in a failover clustered configuration, avoiding SPOF and implementing redundancy. 
  #### Encryption
  Converting plaintect to cyphertect. protects confidentiality and integrity 


## Chapter 9:
  




