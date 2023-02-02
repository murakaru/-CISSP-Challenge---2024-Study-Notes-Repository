
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
-- Proactive approach: during design and development.  It is a defensive approach to threat modelling: takes place during initial design. Based on predicting threats and designing specific defenses during the coding and crafting process.
-- Reactive approach: once product is created and deployed. Takes care of the threats that could not be predicted during the design phase. It addresses unforeseen issues. This is known as thrat hunting or adversarial approach.

Microsoft SDLC goals in threat modelling 

-- Reduce sec related design and coding defects 
-- Reduce severity of remaining threats

Fuzz testing: dynamic testing technique that provides many different types of input to software to stress its limits and find previously undetected flaws


**Identifying threats**
How do we indentify threats? 

Focus on Assets: Determine the value of assets bafore identifying the threats 
Focus on Attackers: Identify attackers and their motivations, goals, TTPs 
Focus on Software: This is specific to comapanies that develops software. 

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

-- Trust Boundaries : Any location where the level of trust or security changes
-- Dataflow Paths: The movement of data between locations
-- Input Points: Locations where external input is received
-- Privileged Operations: Any activity that requires greater privileges than of a standard user account or process, typically required to make system changes or alter security
-- Details about Security Stance and Approach: The declaration of the security policy, security foundations, and security assumptions


Once threats are identified, they should be fully documented by defining the means, target, and consequences of a threat.

**Prioritization and Response**

After documentation, the next step is to rank or rate the threats. This can be accomplished using a wide range of techniques, such as Probability × Damage Potential ranking, high/medium/low rating, or the DREAD system.

The Disaster, Reproducibility, Exploitability, Affected Users, and Discoverability (DREAD)

-- Damage Potential: How severe is the damage likely to be if the threat is realized?
-- Reproducibility: How complicated is it for attackers to reproduce the exploit?
-- Exploitability: How hard is it to perform the attack?
-- Affected Users: How many users are likely to be affected by the attack (as a percentage)?
-- Discoverability: How hard is it for an attacker to discover the weakness?


### Defence in depth 

Terms related to defense in depth:  Layering, levels, classifications, zones , realms , compartments , Silos , segmentations, lattice structure, and protection rings
Multiple contols in series - One after the other. 
Objective: No one control can protect against all threats 

