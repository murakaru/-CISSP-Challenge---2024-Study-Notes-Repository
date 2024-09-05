# Domain 6: Security Assessment and Testing

Chapter 15: Design and validate assesment,test and audit strategies| Conduct security Control Testing | Conduct security Audits
Chapter 18: Training and awareness | Disaster Recovery 

### Introduction. 

Security assessment includes various tools: 
1. vulnerability assessments
2. penetration tests
3. software testing
4. audits

#### Chapter 15: Design and validate assesment,test and audit strategies

* Internal Audit
An organization’s security staff can perform security tests and assessments, and the results are meant for internal use only, designed to evaluate controls with an eye toward finding potential improvements
An internal audit strategy should be aligned to the organization’s business and day-to-day operations

* External Audit
An external audit strategy complements the internal strategy.
They are performed by an outside auditing firm. 

* Third-party Audit

These are conducted by, or on behalf of, another org
In the case of a third-party audit, the org initiating the audit generally selects the auditors and designs the scope of the audit.The statement on Standards for Attestation Engagements document 18 (SSAE 18), titled Reporting on Controls, provides a common standard to be used by auditors. The report is shared with customers and potential customers. SSAE 18 and ISAE 3402 engagements are commonly referred to as a service organization controls (SOC) audits

###### Three forms of SOC reports 

* SOC 1: assess the organization’s controls that might impact the accuracy of financial reporting
* SOC 2: assess the organization’s controls that affect the security with a focus on the CIA triad. The results are confidential and are usually only shared outside an org under an NDA. 
* SOC 3: assess the organization’s controls that affect the security with a focus on CIA triad and privacy information stored in a system. The key difference between SOC 2 and SOC 3 is that the SOC3 audit results are intended for public disclosure. 

###### Two types of SOC reports:

* Type I Reports: provide the auditor’s opinion on the description provided by management and the suitability of the design of the controls. They cover only a specific point in time, rather than an extended period

* Type II Reports: They are more detailed than Type I reports. The auditor’s opinion is taken into consideration on the operating effectiveness of the controls. The auditor confirms the controls are functioning properly. These reports also cover an extended period of time, at least 6 months. Type II reports are considered much more reliable than Type I reports. 


#### Conduct security Control Testing

This includes testing of physical facility, logical systems and applications; 

Below are some common testing methods:

##### Vulnerability assessment
Examining systems for these weaknesses - The goal of a vulnerability assessment is to identify elements in an environment that are not adequately protected.
Security Content Automation Protocol (SCAP) - a common framework for discussion and facilitation of automation of interactions between different security systems.
   
###### SCAP components related to vulnerability assessments:
   
* Common Vulnerabilities and Exposures (CVE): provides a naming system for describing security vulnerabilitie
* Common Vulnerability Scoring Systems (CVSS): provides a standardized scoring system for describing the severity of security vulnerabilities; it includes metrics and calc tools for exploitability, impact, how mature exploit code is, and how vulnerabilities can be remediated, and a means to score vulns against users' unqiue requirements
*  Common Configuration Enumeration (CCE): provides a naming system for system config issues
*  Common Platform Enumeration (CPE): provides a naming system for operating systems, applications, and devices
*  Extensible Configuration Checklist Description Format (XCCDF): Provides a language for specifying security checklists
Open Vulnerability and Assessment Language (OVAL): provides a language for describing security testing procedures; used to describe the security condition of a system

##### Penetration testing
Penetration tests goes beyond vulnerability testing techniques because it actually attempts to exploit systems.

###### Phases of Pen testing

* planning: includes agreement on the scope of the test and the rules of engagement
* Information gathering and discovery: uses manual and automated tools to collect information about the target environment
* Basic reconnaissance
* Network discovery - testers probe for system weaknesses using network, web and db vuln scans
* Attack: attempts to defeat system security

The tests of a penetration test are normally categorized into three groups:

* White-box penetration test: sometimes called "known environment" tests. 
provides the attackers with detailed information about the systems they target
the tester has access to the source code and performss testing from a developer's perspective

* Gray-box penetration test: sometimes called "partially known environment" which balance the advantages and disadvantages of white- and black-box penetration tests
the tester evaluates software from a user perspective but has access to the source code

* Black-box penetration test: sometimes called "unknown environment" - does not provide attackers with any information prior to the attack
this simulates an external attacker trying to gain access to information about the business and technical environment before engaging in an attack

##### Log reviews

Security Information and Event Management (SIEM): These systems collect information using the syslog functionality present in many devices, operating systems, and applications

Logging systems should also make use of the Network Time Protocol (NTP) to ensure that clocks are synchronized on systems sending log entries to the SIEM as well as the SIEM itself, ensuring info from multiple sources have a consistent timeline

Information security managers should also periodically conduct log reviews, particularly for sensitive functions, to ensure that privileged users are not abusing their privileges
Network flow (NetFlow) logs are particularly useful when investigating security incidents


##### Synthetic transactions:

Scripted transactions with known expected results
Synthetic monitoring: uses emulated or recorded transactions to monitor for performance changes in response time, functionality, or other performance monitors
Dynamic testing may include the use of synthetic transactions to verify system performance; synthetic transactions are run against code and compare out to expected state

##### Code review and testing

Code review and testing is "one of the most critical components of a software testing program"
These procedures provide third-party reviews of the work performed by developers before moving code into a production environment, possibly discovering security, performance, or reliability flaws in apps before they go live and negatively impact business operations
In code review, AKA peer review, developers other than the one who wrote the code review it for defects

Fagan inspections: the most formal code review process follows six steps:
* planning
* Overview
* preparation
* inspection
* rework
* follow-up

Entry criteria are the criteria or requirements which must be met to enter a specific process
Exit criteria are the criteria or requirements which must be met to complete a specific process
Static application security testing (SAST): evaluates the security of software without running it by analyzing either the source code or the compiled application
Dynamic application security testing (DAST): evaluates the security of software in a runtime environment and is often the only option for organizations deploying applications written by someone else

##### Misuse case testing

Misuse case testing: AKA abuse case testing - used by software testers to evaluate the vulnerability of their software to known risks;focuses on behaviors that are not what the org desires or that are counter to the proper function of a system/app
In misuse case testing, testers first enumerate the known misuse cases, then attempt to exploit those use cases with manual or automated attack techniques

##### Test coverage analysis

A test coverage analysis is used to estimate the degree of testing conducted against new software; to provide insight into how well testing covered the use cases that an app is being tested for
Test coverage: The total number of use cases

Five common criteria used for test coverage analysis:

* branch coverage: has every IF statement been executed under all IF and ELSE conditions?
* condition coverage: has every logical test in the code been executed under all sets of inputs?
* functional coverage: has every function in the code been called and returned results?
* loop coverage: has every loop in the code been executed under conditions that cause code execution multiple times, only once, and not at all?
* statement coverage: has every line of code been executed during the test?
* Test coverage report: measures how many of the test cases have been completed; is used to provide test metrics when using test cases

##### Interface testing

Interface testing assesses the performance of modules against the interface specs to ensure that they will work together properly when all the development efforts are complete
Three types of interfaces should be tested:

* application programming interfaces (APIs):
* user interfaces (UIs)
* physical interfaces: 

##### Breach attack simulations

Breach and attack simulation (BAS): platforms that seek to automate some aspects of penetration testing
The BAS platform is not actually waging attacks, but conducting automated testing of security controls to identify deficencies
A BAS system combines red team (attack) and blue team (defense) techniques together with automation to simulate advanced persistent threats (and other advanced threat actors) running against the environment
Designed to inject threat indicators onto systems and networks in an effort to trigger other security controls (e.g. place a suspicious file on a server)
detection and prevention controls should immediately detect and/or block this traffic as potentially malicious

##### Compliance checks

Orgs should create and maintain compliance plans documenting each of their regulatory obligations and map those to the specific security controls designed to satisfy each objective
Compliance checks are an important part of security testing and assessment programs for regulated firms: these checks verify that all of the controls listed in a compliance plan are functioning properly and are effectively meeting regulatory requirements

Managers should periodically inspect the results of backups to verify that the process functions effectively and meets the organization’s data protection needs
this might include reviewing logs, inspecting hash values, or requesting an actual restore of a system or file

#### Chapter 18: Training and awareness | Disaster Recovery

##### Training and awareness

Training and awareness programs play a crucial role in preparing an organization’s workforce to support information security programs
They educate employees about current threats and advise them on best practices for protecting information and systems under their care from attacks
Program should begin with initial training designed to provide foundation knowledge to employees who are joining the org or moving to a new role; the initial training should be tailored to an individual’s role
Training and awareness should continue to take place throughout the year, reminding employees of their responsibilities and updating them on changes to the organization’s operating environment and threat landscape
Use phishing simulations to evaluate the effectiveness of their security awareness programs

##### Disaster Recover (DR) and Business Continuity (BC)

Business Continuity (BC): the processes used by an organization to ensure, holistically, that its vital business processes remain unaffected or can be quickly restored following a serious incident
Disaster Recovery (DR): is a subset of BC, that focuses on restoring information systems after a disaster
These processes need to be periodically accessed, and regular testing of disaster recovery and business continuity controls provide organizations with the assurance they are effectively protected against disruptions to business ops
Protection of life is of the utmost importance and should be dealt with first before attempting to save material things


