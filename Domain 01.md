
## Domain 1: Security and Risk Management  

- CIA triad
- Security Concepts 
- Security Controls and Security Control Frameworks 
- Threat Modeling
- Security Program Development
- Security Governance
- Ethics

## Security Concepts 

This section aims to explain the *CIA* triad, *AAA* security framework and other security definitions e.g authenticity, accountability, non-repudiation and assurance. 


For information about the CIA triad, [click here](https://murakaru.com/career-blog-1/f/building-secure-systems)
- Opposite of CIA triad is **DAD** which stands for Disclosure,Alteration and Destruction. 
- Other key security definitions are described in the cyber security must know [blog](https://murakaru.com/career-blog-1/f/building-secure-systems?blogcategory=Cybersecurity+Posts+) include: Authenticity, Accountability, Non-repudiation and assurance


- Differences between vulnerability, threat, risk, exposure and control - These terms are easily glosssed over however, its imperative for security teams to undestand the differences inorder to avoid confusion. 
- Here is a pretty neat diagram I created that shows the differences and relationship between security concepts. 


## Security Governance Principles

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


## Security Control Frameworks 

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
  


**NIST Frameworks**

- NIST 800-53 Rev. 5
- NIST Risk Management Framework
- NIST Cybersecurity Framework

**Other Frameworks to note**

- Sherwood Applied Vusiness Security Architecture (SABSA): This is an open standard for security infrastructure development 
- Capability Maturity Model (CMMI): Software developers maturity rating 
- Six Sigma: Developed for identifying manufacturing defects but can be used to measure the success factors of security framework.

**Due Diligence vs Due Care**

So how due you disapprove **negligence** in the occurrence of a loss?  Due Diligence and Due Care. What's the difference between the two? 


**Definition of terms**

- **Standards**: Compulsory requirements for the homogenous use of hardware, software, technology, and security controls. 

- **Baselines**: The minimum level of security that every system throughout the organization must meet

- **Guidelines**: Recommendations on how standards and baselines are implemented and serves as an operational guide for both security professionals and users

- **Procedures**: A document definining/describing exact actions neccessary to implement mechanisms, controls of solutions 

- **Acceptable use policy (AUP)**: A document that defines the acceptable performance and expectation of behaviour. 

- **Security policy**: A document that defines the scope of security needed by the organization. It discusses the assets that require protection and the extent to which security solutions should go to provide the necessary protection.


## Threat Modelling 
 
Threat modelling can be performed proacively or reactively. In both cases, a threat is identified,categorised and analysed. 

Below is an illustration showing the basic steps of threat modelling. 



**Identifying Threats**

Which guidance or references should be used to identify and categorise threats. 

**STRIDE**: Developed by Microsoft




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
