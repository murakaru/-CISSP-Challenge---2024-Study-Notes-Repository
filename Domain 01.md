
# Domain 1: Security and Risk Management  

With reference to the official guide, Domain 1 contains the below chapter and contents 


- Chapter 1 : Security concepts | Security Governance principles | Threat Modelling | SCRM 
- Chapter 2: Personnel Sec Policies | Risk Management concepts | Security awareness and training 
- Chapter 3: Business Continuity Planning 
- Chapter 4: Compliance | Legal and regulatory issues 
- Chapter 19: Code of ethics | Investigation Types 


## Chapter 1 
### Security concepts 

This section aims to explain the *Security concepts* below
- CIA trid
- DAD 
- IAAA

**CIA Triad**
- *Confidentiality*: The goal of confidentiality protection is to prevent or minimize unauthorized access to data. Confidentiality protections prevent disclosure while protecting authorized access. In an organization, confidentiality can be enhanced through the implementation of design principles, such as the principle of least privilege. The principle of least privilege limits users' access to only the information they need to complete work-related tasks.Some critical definitions to undertand while discussing confidentiality include:
  - Sensitivity - Quality of infor that can cause harm if disclosed.
  - Discretion - Act or decision to control disclosure of information
  - Criticality - Level to which information is mission critical.
  - Concealment - Hiding information (concept of security through obscurity is closely related)
  - Secrecy - Keepy information hidden
  - Privacy - Keeping PII confidential to prevent harm of users .
  - Seclusion - Intentional isolation of information
  - Isolation - keeping information away from the users.
    
- *Integrtity*: concept of protecting the reliability and correctness of data.
Integrity protection prevents unauthorized alterations of data. Properly implemented integrity protection provides a means for authorized changes while protecting against intended and malicious unauthorized activities (such as viruses and intrusions) as well as mistakes made by authorized users (such as accidents or oversights).
Integrity is dependent on confidentiality and access control. Some concepts around integrity
1. Accuracy - Ensuring the information is correct and precise
2. Truthfulness - A reflection of the reality
3. Validity - Being factually or logically sound
4. Accountability - Being accountable or responsible for the actions on information
5. Responsibility - Taking charge over someone or something
6. Completeness - Having all the necessary components
7. comprehensiveness - Being complete in scope.
   
- *Availablity*: Availability means authorized subjects are granted timely and uninterrupted access to objects.
  This means that the users are protected against DDoS attacks and infra issues that may discrupo access to information.
  This involves having reliable performance, redundancy, reliable backups and preventing data loss or destruction.
  Availabilty is dependent on confidentiality and Integrity. Without these, availabity cannot be achieved.
  Some concepts of availability are
  1. Usability - How easy is t to use the data? How easy is it to learn and understand the information
  2. Accessibility - Are we certain that a wide variery of individuals can access this information taking their limitations and capability into account
  3. Timeliness - Are the resources available when needed? 


![image](https://user-images.githubusercontent.com/19290577/213007046-ed4c256b-afd5-4717-9a35-710e7f4ae840.png)


- Too much confidentiality = difficulty to access data = reduced availability 
- Too much Integrity = slow down access = Cause delay in data usage = affects availability.
- Too much availablity = Confidentiality and integrity will suffer 

A balance of the three is required. 

Threats to confidentiality 
- Cryptanalysis - Attack on encryption 
- Social Engineering 
- Key loggers 
- IOT 

Countermeasures 

- For data at rest - encyption using AES256 full disk encyption
- For data in motion - Use Secure transport protocols e.g SSL, TLS or IPSEC
- For data in Use: Adopt best practises -m clean desk, no shoulder surfing r.t.c 
- Strong passwords, MFA , masking , access control , need to know, least priviledge.

Threats to integrity 

- Alteration of data
- Code injection
- Cryptanalysis 

Countermeasures 

- Cryptography 
- Checksums 
- Message Digest 
- Digital signatures 
- Access control 

Threats to Availability 

- Malicious Attacks e.g DDoS, physical system compromise, disgruntled employees revenge 
- Application errors - code error in app
- Component failure e.g failed hardware
- Human error - oversight or misconfiguration in a security policy 

Countermeasures 

- IPS/IDS 
- Patch management - Prior verification of patch before installation to rule out vulnerability possibility 
- Redundancy - Active/standby configuration . RAID(having data on multiople disks) 
- SLA - if using third party services e.f vendors, contractors and consultants. 


Opposite of CIA triad is **DAD** which stands for Disclosure,Alteration and Destruction. 

**DAD triad**

![image](https://user-images.githubusercontent.com/19290577/213008411-eb48d484-d9bc-4ea0-9b2b-0b8ac97b8cce.png)


- Other key security definitions are described in the cyber security must know include: Authenticity, Accountability, Non-repudiation and assurance


 **IAAA** 
 
 
 - Identification: Username, IP address, Phone number e.t.c 
 - Authentication: Prove the identification e.g psomething you know (password), something you have (ID card, passport), something you are (biometrics)
 - Authorization: What are you allowed to access? What are the proviledges of the account? Role based access (RBAC)
 - Auditing: Tracing an action to an identity through log collection
 - Accounting: Proof that a specific user performed an action in the system


## Protection mechanisms

### defence in depth 
Also called layering
using multiple security controls in series. Security analysts perform the controls linearly. 

### Abstraction
This is used for efficiency 
Abstraction means classifying related elements , groups and roles.
By abstracting the related elements, a security analyst can apply the same controls across board hence making administration processes easier. 

### data Hiding 
Preventing data from being accessed.
The subject cannot see or access the data 
How can we achieve data hiding? 
1. Keep a db from being accessed by unauthorised persons
2. Prevent/limiting   app from accessing HW

An example of data hiding: Stenography 
Example: Multilevel secure system. There are multiple processes running across the different levels of the system. With data hiding, a sec analyst can ensure that the processes at one level cannot access data existing at a different system level.How can we achieve this? Place the data objects in security containers that is different form the subject objects.
Security through obscurity - This is a litte different. It is the deliberate practise of not informing a subject about an object being [resent and hence preventing them form discovering and accessing the data object. 
This is not a form of protection.

### Encryption 
Hiding meaning of the data. Converting plaintect to ciphertext.

## Security Boundaries 

What is a sec boundary?
An intersection point between two areas - subnets, perimeter - that have different sec requirements. 
Exists betwen high sec area and low sec area. These need to be clearly defined.


### Security Governance principles
Who performs security governance? BoD or CEO or CISO 
What is sec governance? This is how we compare sec processes and infrastrure within an organisation with knowledge and insights obtained from external structure.
Which external frameworks can be used? NIST SP 800-53 and NIST SP 800-100. 

This section explains how organizations should align their security function to business strategy, goals, mission, and objectives. 
We will also look into the organizational roles and responsibilities from a security perspective and the common Security control frameworks that organizations can align with as they design their security strategy. 

**Types of Security Controls**

- **Administrative**: Security documentation, risk management, personnel security, and training
- **Technical**: Software or hardware components e.g firewalls, IDS, encryption, and identification and authentication mechanisms.
- **Physical**: Security guards, locks, fencing, and lighting.

Controls provide **Defence in Depth** which is a layered security approach. If one line of defense is compromised, additional layers exist as a backup to ensure that threats are stopped along the way. 

**Functionalities of security controls**
- **Preventive** Intended to avoid an incident from occurring
- **Detective** Helps identify an incident’s activities and potentially an intruder
- **Corrective** Fixes components or systems after an incident has occurred
- **Deterrent** Intended to discourage a potential attacker
- **Recovery** Intended to bring the environment back to regular operations
- **Compensating** Controls that provide an alternative measure of control


**Security Control Frameworks**

Security control Frameworks form the foundation for security programs. By adopting Security control frameworks,you can apply proven security practises to your organizations. Frameworks are generic and can be used across multiple industries. 

**Common Security Control Frameworks**

1. **ISO/IEC 27000 series** - This is a joint standard for Information Security Management (ISM) 

- **ISO 27001** -Information Security Management Requirements for **governance**
  - Examines the risks of an organization e.g threats, vulnerabilities. 
  - Uses the above information to develop policies. 
  - Designs and implements suite of information security controls (defined in 27002) to address and manage the risks. 
  - Ensures that security practises are followed to ensure that the security controls meet the organizations security needs on an ongoing basis
  - Plan -> Do -> Check ->Act.  
  - Measure twice and cut one. 
  - Example: GDPR

- **ISO 27002** - Information **Security Controls defined** to achieve your mission as an organization. The goal is to implement policies, assign responsibilities and prescribe proceedures for applying integrated, layered protection for Information Systems. 
There are 12 security controls defined 

  - Risk assesment 
  - Security policy 
  - Organization Information Security 
  - Asset Management 
  - Human Resource Security 
  - Physical and Environmental Security 
  - Communication and operational Management 
  - Access Controls 
  - Information System Acquisition, development and maintenance 
  - Information Security Incident management 
  - Business Continuity Management 
  - Compliance - Ensuring conformance 

Nb/ Note the difference between 27001 and 27002 for the CISSP exam

2. **Committee Of Sponsoring Organizations (COSO)**

  This one places an emphasis on how to identify and manage financial risks e.g Fraud prevention by     implementing a system for financial checks and balances.

3. **Information Technology Infrastructure Library (ITIL)**

  ITIL focuses on understanding how IT and security needs to be integrated with and aligned to the objectives of an organization
  A best practise document for IT service management. 

4. **PCI-DSS**

  Payment Card Data Security Standards - Provides standards that must be followed for any organization that accepts cards or any form of electronic payments. 


5. **Control Objectives for Information and Related Technology (COBIT)**

  Used by auditors and planning committee 

**Elements of Cobit**
- Organization design/strategy
- People
- Processes 
- Technology 

**Dynamic Interconnection Factors**
- Governance 
- Culture 
- Enablement
- Emergence
- Human Factors
- Architecture

**PDCA - (Plan -> Do ->Check ->Act) - Cobit**

  This creates a flexible standard that sets expections for problem solving and cjhange management teams. It ensures that the organization is safe from security risks 
  
**NIST RMF**

- NIST 800-53 Rev. 5
- NIST Risk Management Framework (RMF) 
- NIST Cybersecurity Framework

## The Nist RMF

https://csrc.nist.gov/projects/risk-management/about-rmf

There are seven steps in the RMF:
  
- prepare: Prepare refers to activities that are necessary to manage security and privacy risks before a breach occurs
- categorize:which is used to develop risk management processes and tasks. Security professionals then use those processes and develop tasks by thinking about how the confidentiality, integrity, and availability of systems and information can be impacted by risk.
- select: Select means to choose, customize, and capture documentation of the controls that protect an organization. An example of the select step would be keeping a playbook up-to-date or helping to manage other documentation that allows you and your team to address issues more efficiently.
- implement:implement security and privacy plans for the organization. Having good plans in place is essential for minimizing the impact of ongoing security risks. 
- assess:Assess means to determine if established controls are implemented correctly. An organization always wants to operate as efficiently as possible. So it's essential to take the time to analyze whether the implemented protocols, procedures, and controls that are in place are meeting organizational needs.
- authorize:Authorize means being accountable for the security and privacy risks that may exist in an organization. As an analyst, the authorization step could involve generating reports, developing plans of action, and establishing project milestones that are aligned to your organization's security goals.
- monitor:Monitor means to be aware of how systems are operating. Assessing and maintaining technical operations are tasks that analysts complete daily. Part of maintaining a low level of risk for an organization is knowing how the current systems support the organization's security goals. If the systems in place don't meet those goals, changes may be needed.

 ### NIST CSF

The core functions of the NIST CSF provide specific guidance and direction for security professionals
This framework is used to develop plans to handle an incident appropriately and quickly to lower risk, protect an organization against a threat, and mitigate any potential vulnerabilities.  


**functions of the NIST Cybersecurity Framework**

Components of the CSF
The framework consists of three main components: the core, tiers, and profiles. In the following sections, you'll learn more about each of these CSF components.

Core
The CSF core is a set of desired cybersecurity outcomes that help organizations customize their security plan. It consists of five functions, or parts: Identify, Protect, Detect, Respond, and Recover. These functions are commonly used as an informative reference to help organizations identify their most important assets and protect those assets with appropriate safeguards. The CSF core is also used to understand ways to detect attacks and develop response and recovery plans should an attack happen.

Tiers
The CSF tiers are a way of measuring the sophistication of an organization's cybersecurity program. CSF tiers are measured on a scale of 1 to 4. Tier 1 is the lowest score, indicating that a limited set of security controls have been implemented. Overall, CSF tiers are used to assess an organization's security posture and identify areas for improvement.

Profiles
The CSF profiles are pre-made templates of the NIST CSF that are developed by a team of industry experts. CSF profiles are tailored to address the specific risks of an organization or industry. They are used to help organizations develop a baseline for their cybersecurity plans, or as a way of comparing their current cybersecurity posture to a specific industry standard.


* identify - What  risks pose a threat in my environment?
* protect - What stategy can i use to protect the org? 
* detect - Identifying the actual incidents and improve monitoring to improve detection
* respond - Ensuring that proper procedures are used to contain, neutralise and analyse security incidents. 
* recover - Returing the affected systems to normal operation

Implementing the CSF
In any scenario, the U.S. Cybersecurity and Infrastructure Security Agency (CISA) provides detailed guidance that any organization can use to implement the CSF. This is a quick overview and summary of their recommendations:

Create a current profile of the security operations and outline the specific needs of your business.

Perform a risk assessment to identify which of your current operations are meeting business and regulatory standards.

Analyze and prioritize existing gaps in security operations that place the businesses assets at risk.

Implement a plan of action to achieve your organization’s goals and objectives.


OWASP security Principles

- The first OWASP principle is to minimize the attack surface area. An attack surface refers to all the potential vulnerabilities that a threat actor could exploit, like attack vectors, which are pathways attackers use to penetrate security defenses. Examples of common attack vectors are phishing emails and weak passwords
  
- The principle of least privilege means making sure that users have the least amount of access required to perform their everyday tasks. The main reason for limiting access to organizational information and resources is to reduce the amount of damage a security breach could cause.

- The next principle we'll discuss is defense in depth. Defense in depth means that an organization should have multiple security controls that address risks and threats in different ways. One example of a security control is multi-factor authentication, or MFA, which requires users to take an additional step beyond simply entering their username and password to gain access to an application

- nother principle is separation of duties, which can be used to prevent individuals from carrying out fraudulent or illegal activities. This principle means that no one should be given so many privileges that they can misuse the system

- Keep security simple is the next principle. As the name suggests, when implementing security controls, unnecessarily complicated solutions should be avoided because they can become unmanageable.
  
- The last principle is to fix security issues correctly. Technology is a great tool, but can also present challenges. When a security incident occurs, security professionals are expected to identify the root cause quickly.

**Other Frameworks to note**

- Sherwood Applied Vusiness Security Architecture (SABSA): This is an open standard for security infrastructure development 
- Capability Maturity Model (CMMI): Software developers maturity rating 
- Six Sigma: Developed for identifying manufacturing defects but can be used to measure the success factors of security framework.

The Federal Energy Regulatory Commission - North American Electric Reliability Corporation (FERC-NERC)
FERC-NERC is a regulation that applies to organizations that work with electricity or that are involved with the U.S. and North American power grid. These types of organizations have an obligation to prepare for, mitigate, and report any potential security incident that can negatively affect the power grid. They are also legally required to adhere to the Critical Infrastructure Protection (CIP) Reliability Standards defined by the FERC. 


The Federal Risk and Authorization Management Program (FedRAMP®)
FedRAMP is a U.S. federal government program that standardizes security assessment, authorization, monitoring, and handling of cloud services and product offerings. Its purpose is to provide consistency across the government sector and third-party cloud providers. 


Center for Internet Security (CIS®)
CIS is a nonprofit with multiple areas of emphasis. It provides a set of controls that can be used to safeguard systems and networks against attacks. Its purpose is to help organizations establish a better plan of defense. CIS also provides actionable controls that security professionals may follow if a security incident occurs. 

General Data Protection Regulation (GDPR)
GDPR is a European Union (E.U.) general data regulation that protects the processing of E.U. residents’ data and their right to privacy in and out of E.U. territory. For example, if an organization is not being transparent about the data they are holding about an E.U. citizen and why they are holding that data, this is an infringement that can result in a fine to the organization. Additionally, if a breach occurs and an E.U. citizen’s data is compromised, they must be informed. The affected organization has 72 hours to notify the E.U. citizen about the breach.


**Due Diligence vs Due Care**

So how due you disapprove **negligence** in the occurrence of a loss?  Due Diligence and Due Care. What's the difference between the two? 


**Definition of terms**

- **Standards**: Compulsory requirements for the homogenous use of hardware, software, technology, and security controls. 

- **Baselines**: The minimum level of security that every system throughout the organization must meet

- **Guidelines**: Recommendations on how standards and baselines are implemented and serves as an operational guide for both security professionals and users

- **Procedures**: A document definining/describing exact actions neccessary to implement mechanisms, controls of solutions 

- **Acceptable use policy (AUP)**: A document that defines the acceptable performance and expectation of behaviour. 

- **Security policy**: A document that defines the scope of security needed by the organization. It discusses the assets that require protection and the extent to which security solutions should go to provide the necessary protection.


### Threat Modelling 
 
Threat modelling can be performed proacively or reactively. In both cases, a threat is identified,categorised and analysed. 


**Identifying Threats**

Which guidance or references should be used to identify and categorise threats. 

**STRIDE**: Developed by Microsoft

Here is a breakdown of the Stride model - definitions + Security controls 

![image](https://user-images.githubusercontent.com/19290577/213023333-3536984e-e9ea-4fba-8d9b-1a53bbc66037.png)


**PASTA** 

PASTA is the Process for Attack Simulation and Threat Analysis. 
PASTA threat modelling combines an attacker perspective of a business with risk and impact analysis to create a complete picture of the threats to products and applications, their vulnerability to attack, and informing decisions about risk and priorities for fixes.

**VAST**

Visual, Agile, and Simple Threat (VAST) 
Integrates threat and risk management into an Agile programming environment on a scalable basis

**DREAD**

The Disaster, Reproducibility, Exploitability, Affected Users, and Discoverability (DREAD)

- Damage Potential: How severe is the damage likely to be if the threat is realized?
- Reproducibility: How complicated is it for attackers to reproduce the exploit?
- Exploitability: How hard is it to perform the attack?
- Affected Users: How many users are likely to be affected by the attack (as a percentage)?
- Discoverability: How hard is it for an attacker to discover the weakness?

**Reduction Analysis**

Trust Boundaries   Any location where the level of trust or security changes
Dataflow Paths   The movement of data between locations
Input Points   Locations where external input is received
Privileged Operations   Any activity that requires greater privileges than of a standard user account or process, typically required to make system changes or alter security
Details about Security Stance and Approach   The declaration of the security policy, security foundations, and security assumptions

### SCRM 

Understand what Supply chain is and the impact on security 

Most computers, devices, networks, systems, and even cloud services are not built by a single entity.
Often the CPU, memory, drive controllers, hard drives, SSDs, and video cards are created by other third-party vendors

Definition: Supply chain risk management (SCRM) is the means to ensure that all of the vendors or links in the supply chain are reliable, trustworthy, reputable organizations that disclose their practices and security requirements to their business partners (although not necessarily to the public).
The goal of a secure supply chain is to ensure that the finished product is of sufficient quality, meets performance and operational goals, and provides stated security mechanisms, and that at no point in the process was any element counterfeited or subjected to unauthorized or malicious manipulation or sabotage. 


# Chapter 2 

## Personnel Sec Policies  

How to create and enforce personnel sec policies in the workplace 

## Risk Management concepts

**Threats vs Vulnerabilities**
* Threats: any potential occurrence that many cause an undersirable or unwanted outome for a specific asset; they can be intentional or accidental; loosely think of a threat as a weapon that could cause harm to a target
* Vulnerability: the weakness in an asset, or weakness (or absense) of a safeguard or countermeasure; a flaw, limitation, error, frailty, or susceptibility to harm
  

- Exposure is risk, and risk is mitigated by safeguards
Safeguards protect assets that are endangered by threats
- Threat Agent/Actors: intentionally exploit vulnerabilities
- Threat Events: accidential occurrences and intentinoal exploitations of vulnerabilities
- Threat Vectors: (AKA attack vector) is the path or means by which an attack or attacker can gain access to a target in order to cause harm
  
- Exposure: being susceptible to asset loss because of a threat; the potential for harm to occur
- Exposure Factor (EF): derived from this concept; an element of quantitative risk analysis that represents the percentage of loss than org would experience if a specific asset were violated by a realized risk
- Single Loss Expectancy (SLE): an element of quantitative risk analysis that represents the cost associated with a single realized risk against a specific asset; SLE = asset value (AV) * exposure factor (EF)
- Annualized rate of occurrence (ARO): an element of quantitative risk analysis that represent the expected frequency with which a specific threat or risk will occur within a single year
- Annualized loss expectancy (ALE): an element of quantitative risk analysis that represent the possible yearly cost of all instances of a specific realized threat against a specific asset; ALE = SLE * ARO
Safeguard evaluation: ALE for an asset if a safeguard is implemented; ALE before safeguard - ALE with safeguard - annual cost of safeguard, or (ALE1 - ALE2) - ACS
Risk: the possiblity or likelihood that a threat will exploit a vulnerability to cause harm to an asset and the severity of damage that could result; the > the potential harm, the > the risk

**Risk assessment/analysis**

used to identify the risks and set criticality priorities, and then risk response is used to determine the best defense for each identified risk
Risk is threat with a vulnerability
Risk = threat * vulnerability (or probability of harm multiplied by severity of harm)
Addressing either the threat or threat agent or vulnerability directly results in a reduction of risk (known as threat mitigation)

**Risk response**

the formulation of a plan for each identified risk; for a given risk, you have a choice for a possible risk response:
* Risk Mitigation: reducing risk, or risk mitigation, is the implementation of safeguards, security controls, and countermeasures to reduce and/or eliminate vulnerabilities or block threats
* Risk Assignment: assigning or transferring risk is the placement of the responsibility of loss due to a risk onto another entity or organization; AKA assignment of risk and transference of risk
* Risk Deterrence: deterrence is the process of implementing deterrents for would-be violators of security and policy 
e.g. implementing auditing, security cameras, and warning banners; using security guards
* Risk Avoidance: determining that the impact or likelihood of a specific risk is too great to be offset by potential benefits, and not performing a particular business function due to that determiniation; the process of selecting alternate options or activities that have less associated risk than the default, common, expedient, or cheap option
* Risk Acceptance: the result after a cost/benefit analysis determines that countermeasure costs would outweigh the possible cost of loss due to a risk
also means that management has agreed to accept the consequences/loss if the risk is realized
* Risk Rejection: an unacceptable possible response to risk is to reject risk or ignore risk; denying that risk exists and hoping that it will never be realized are not valid prudent due care/due diligence responses to risk
* Risk Transference: paying an external party to accept the financial impact of a given risk
  
Inherent Risk: the level of natural, native, or default risk that exists in an environment, system, or product prior to any risk management efforts being performed (AKA initial or starting risk); this is the risk identified by the risk assessment process
Residual Risk: consists of threats to specific assets against which management chooses not to implement (the risk that management has chosen to accept rather than mitigate); risk remaining after security controls have been put in place
Total Risk: the amount of risk an org would face if no safeguards were implemented
Conceptual Total Risk Formula: threats * vulnerabilities * asset value = total risk
Controls Gap: amount of risk that is reduced by implementing safeguards, or the difference between total risk and residual risk
Conceptual Residual Risk Formula: total risk - controls gap = residual risk
Risk should be reassessed on a periodic basis to maintain reasonable security because security changes over time

# Chapter 3 
## BCP 
This nvolves assessing the risk to organizational processes and creating policies, plans, and procedures to minimize the impact those risks might have on the organization if they were to occur

BCP is used to maintain the continuous operation of a business in the event of an emergency, with a goal to implement a combination of policies, procedures, and processes
BCP has four distinct phases:
* project scope and planning
* business impact analysis
* continuity planning
* approval and implementation
  
Business continuity requires a lot of planning and preparation; actual implementation of business continuity processes occur quite infrequently
The primary facets of business continuity are:

* Resilience: (e.g. within a data center and between sites or data centers)
* Recovery: if a service becomes unavailable, you need to recover it as soon as possible
* Contingency: a last resort in case resilience and recovery prove ineffective

**Business continuity**

**Project Scope and planning**
Developing the project scope and plan starts with gaining support of the management team, making a business case (cost/benefit analysis, regulatory or compliance reasons etc.) and gaining approval to move forward.
Next, you need to form a team with representatives from the business as well as IT
Next, start with a business continuity policy statement, then conduct a business impact analysis (see next item), and then develop the remaining components:

*preventive controls
*relocation
*the actual coninuity plan
*testing
*training and maintenance

# Chapter 4 
## Compliance

The act of confirming or adhering to rules, policies, regulations, standards, or requirements
on a personnel level, compliance is related to individual employees following company policies and procedures
employees need to be trained on company standards as defined in the security policy and remain in compliance with any contractual obligations (e.g. with PCI DSS)

**Laws**

Categories of laws

1. Criminal laws
2. Civil laws
3. Administrative laws

##### Laws 
1. computer crime 
2. Computer Fraud and Abuse act 
3. CFAA amendments 
4. National Information Infrastructure Protection Act of 1996 

Federal Sentensing Guideline 
Federal Information Security Management Act 
Federal Cybersecurity Laws of 2014 
Intellectual Property (IP)
Copyright and digital Millenium Copyright Act 


Trademarks 
Patents 
Trade secrets 
Licensing 
Import /Export 
Countries of concern 
Encryption Export Contreols 

###### Privacy 

US Privacy Law 
  Fourth Amendment 
  Privacy act of a974 
  Electronic communications Provacy Act 
  Communicationns Assistance for Law enforcement Act 
  Economic espionage Act of 1996 
  Health Insurance portability and Accountability Act of 1996 
  Health Information Technology for economic and Clinical Health Act of 2009 
  Childrens online privacy protection Act of 1998 
  Gramm-Leach-Bliley Act of 1999 
  USA patriot Act of 2001
  Family Educational Rights and Privacy Act 
  Identity Theft and Assumption Detterence Act 

  European Union Privacy Law 
  European Union Data Protection Directive (DPD)
  European Union general data protection Regulation 
  Cross border Infromation sahring 

#### Canadian Privacy Law 
Impacts canadian residents 
PIPEDA - Personall Infor Protection and Electronic Documents Act - Restricts the collection, use and disclosure of personal information.
Provisions under PIPEDA 
1. Race, nationality and ethinicity
2. religion
3. Age
4. Marital status
5. Medical, education and employment history
6. Financial information
7. DNA
8. Identifying numbers
9. Employee performance records

So what is excluded?
1. Infor that is not about an individual
2. Infor about a business
3. Infor that is rendered anonymous - as long as you cant link the infor to someone
4. Infor about public servants
5. Business contact infor collected for purposes of employment, business or profession.

PIPEDA may be superseded by province -specific laws. These exists in Alberta, British colombia and Quebec 

  
#### State privacy Laws
These are passed by the state, provinces and other jurisdictions 
E.g California Consumer privacy Act - This is modelled after GDPR.
It provides the below
1. Right to know the infor that businesses are collecting
2. Right to be forgotten
3. Right to opt of of sale of information
4. Right to exercise privacy rights without discrimination
   
#### Compliance 

* PCI DSS 

The PCI DSS requirements 
1. Install FW to protect cardholder data
2. Do nopt use vendor supplied defaults e.g system passwords
3. Protect the stored cardholder data
4. Encrypt the transmission of card holder data
5. Protect all systems against Malware
6. Have secure systems and apps
7. Restrci access to - need to know
8. Identify and authenticate access to systems
9. restrict physical access to the data
10. Track and monitor all access
11. Maintain a policy that addresses infor sec for all.

# Chapter 19 

Hand written notes of chapter 19 

![image](https://user-images.githubusercontent.com/19290577/214577001-6cf67fbc-ad2d-45ee-b793-475d3bf7e39c.png)

![image](https://user-images.githubusercontent.com/19290577/214587948-65eade03-f073-4054-8003-beb40ff673ac.png)

![image](https://user-images.githubusercontent.com/19290577/214587807-9ce67e01-e97d-4e06-b92f-7c06b6d6cd00.png)


**Code of ethics**

![image](https://user-images.githubusercontent.com/19290577/214586834-330bba0b-bf44-4126-ae9e-8bc3943a8dc6.png)

**Investigation Types** 

1. Adminstrative Investigations: internal - Examine operational issues or the violations of an orgs policies. The goal is to resolve operational issues. Helps to conduct the RCA of an issue. 
2. Criminal Investigations: Conducted by law enforcement. Investigates violation of a law and seeks prosecution in criminal court. This investigation must meet "beyond reasonable doubt" 
3. Civil Investigations: Involves internal employees and outside consultants. They ise the weaker preponderence of evidence standard. 
4. Regulatory: Conducted by govt agencies believing that an org has violated an administrative lae . Regulators conduct these investigations. 



