# Domain 2: Asset Security 

- Chapter 5: Identify and classify information and assets, Establish information and asset handling requirements, Manage data lifecycle.

- Chapter 16: Provision resources securely. 

### Identify and classify information and assets

#### What are assets? 
These are the elements that an organization aims to protect. There are multiple types of assets and hence its important to prioritize the assets. We prioritize the assets based on the threats 

#### What is a threat? 
A threat is any circumstance or event that can negatively impact assets. 

#### What is a vulnerabilities? 
This is a weakness that can be exploited by a threat. 


#### What is a Risk?
Anything that can impact the confidentiality, integrity, or availability of an asset

#### Formula to calculate Risk
Likelihood x Impact = Risk

###### Common asset classifications

Asset classification helps organizations implement an effective risk management strategy. It also helps them prioritize security resources, reduce IT costs, and stay in compliance with legal regulations.

The most common classification scheme is: restricted, confidential, internal-only, and public.

* Restricted is the highest level. This category is reserved for incredibly sensitive assets,  like need-to-know information.

* Confidential refers to assets whose disclosure may lead to a significant negative impact on an organization.

* Internal-only describes assets that are available to employees and business partners.

* Public is the lowest level of classification. These assets have no negative consequences to the organization if they’re released.

### Asset Classification

It's important to identify and classify assets, such as systems, mobile devices etc.

- Classification: derived from compliance mandates, the process of recognizing organizational impacts if information suffers any security compromise (whether to confidentiality, integrity, availability, non-repudiation, authenticity, privacy, or safety)
Asset classifications should match data classification, i.e. if a computer is processing top secret data, the computer should be classified as a top secret asset

- Clearance: relates to access of certain classfication of data or equipment, and who has access to that level or classification

A formal access approval process should be used to change user access; the process should involve approval from the data/asset owner, and the user should be informed about rules and limits before a user is granted access they should be educated on working with that level of classification

Classification levels can be used by businesses during acquisitions, ensuring only personnel who need to know are involved in the assessment or transition

In general, classification labels help users use data and assets properly, for instance by restricting dissemination or use of assets by their classification

#### Asset handling: 
refers to secure transport of media through its lifetime

The data and asset handling key goal is to prevent data breaches, by using:

* Data Maintenance: on-going efforts to organize and care for data through its life cycle
* Data Loss Prevention (DLP): systems that detect and block data exfiltration attempts; two primary types:
   *network-based DLP
   *endpoint-based DLP
* Marking: (AKA labeling) sensitive information/assets ensures proper handling (both physically and electronically)
  
* Data Collection Limitation: prevent loss by not collecting unnecessary sensitive data
  
* Data Location: keep dup copies of backups, on- and off-site
  
##### Data destruction: 

destroy data no longer needed by the organization; policy should define acceptable destruction methods by type and classification (see NIST SP-800-88 for details)

* Erasing: usually refers to a delete operation on media, leaving data remanence
* Clearing: removal of sensitive data from a storage device such that there is assurance data may not be reconstructed using normal functions or software recovery or software recovery utilities; over-writing existing data; it's not very strong, and there's a chance that the data could be brought back
* Purging: removal of sensitive data from a system or device with the intent that data cannot be reconstructed by any known technique; usually refers to mutliple clearing passes combined with other tools; often means getting rid of data in more reliable ways, like using a strong magnetic field (degaussing) to destroy data on storage devices(see below) -- although not considered acceptable for top secret data
* Destruction: includes physically destroying media through shredding, burning, pulverizing, or incinerating, and also includes the use of strong encryption to logically destroy data; a surer way than even purging

### Establish information and asset handling requirements

There are three main categories of cloud-based services:

* Software as a service (SaaS)
SaaS refers to front-end applications that users access via a web browser. The service providers host, manage, and maintain all of the back-end systems for those applications. Common examples of SaaS services include applications like Gmail™ email service, Slack, and Zoom software.

* Platform as a service (PaaS)
PaaS refers to back-end application development tools that clients can access online. Developers use these resources to write code and build, manage, and deploy their own apps. Meanwhile, the cloud service providers host and maintain the back-end hardware and software that the apps use to operate. Some examples of PaaS services include Google App Engine™ platform, Heroku®, and VMware Cloud Foundry. 

* Infrastructure as a service (IaaS)
IaaS customers are given remote access to a range of back-end systems that are hosted by the cloud service provider. This includes data processing servers, storage, networking resources, and more. Resources are commonly licensed as needed, making it a cost-effective alternative to buying and maintaining on premises.

Cloud-based services allow companies to connect with their customers, employees, and business partners over the internet. Some of the largest organizations in the world offer cloud-based services:
- Google Cloud Platform
- Microsoft Azure

##### Cloud security challenges
All service providers do their best to deliver secure products to their customers. Much of their success depends on preventing breaches and how well they can protect sensitive information. However, since data is stored in the cloud and accessed over the internet, several challenges arise:

- Misconfiguration is one of the biggest concerns. Customers of cloud-based services are responsible for configuring their own security environment. Oftentimes, they use out-of-the-box configurations that fail to address their specific security objectives.

- Cloud-native breaches are more likely to occur due to misconfigured services.

- Monitoring access might be difficult depending on the client and level of service.

- Meeting regulatory standards is also a concern, particularly in industries that are required by law to follow specific requirements such as HIPAA, PCI DSS, and GDPR.

#### Components of a sec plan: Policies, standards and Procedures. 

- Policies: Policies are high-level, broad statements that reflect the organization’s general approach to information security. They outline the overall intent, goals, and guiding principles for managing security risks, and typically align with business objectives.
Purpose: Policies provide direction and expectations for security management but do not go into specific details. They often serve as a foundation for the development of standards, guidelines, and procedures.
Example: An organization may have a Security Policy that states "All company data must be protected against unauthorized access."

- Standards: Standards are mandatory, detailed requirements derived from policies. They define specific technical or procedural criteria that must be met to comply with the security policies.
  
Purpose: Standards ensure uniformity and consistency across systems and processes, enabling an organization to implement its policies effectively. They typically cover technical specifications or frameworks that must be followed.

Example: A password standard might specify that "Passwords must be at least 12 characters long and include a combination of upper and lowercase letters, numbers, and symbols."

- Procedures: Procedures are step-by-step instructions that explain exactly how to carry out specific tasks or actions required to comply with policies and standards.
- 
Purpose: Procedures guide personnel through the specific actions needed to achieve consistent outcomes and ensure that security controls are implemented correctly. They are more operational in nature and are used by staff to perform security-related tasks.

Example: A procedure for data backup might detail "how to configure automated backup systems," specifying the steps required for ensuring backups are securely stored and recoverable.

### Manage data lifecycle

* Data at rest: any data stored on media such as hard drives or external media 

* Data in use: data in memory and used by an application. The app should flush memory buffers to remove data after it is no longer needed

* Data in transit: any data transmitted over a network encryption methods protect data at rest and in transit

## Chapter 16

### Provision resources securely

The primary purpose of security operations practices is to safeguard assets such as information, systems, devices, facilities, and apps; these practices help to identify threats, vulnerabilities, and implement controls to reduce the risk to these asssets

Implementing common security operations concepts, along with performing periodic security audits and reviews demonstrates a level of due care

* Need-to-know: a principle that imposes the requirement to grant users access only to data or resources they need to perform assigned work tasks

* Least privilege: a principle stating that subjects are granted only the privileges necessary to perform assigned work tasks and no more

#### Information and asset ownership

Data owner: the person who has ultimate organizational responsibility for data; usually sr. manager (CEO,president, dept. head); data owners typically delegate data protection tasks to others in the org

##### Asset inventory (e.g., tangible, intangible)

- Inventory: complete list of items
- Tangible assets: include hardware and software assets owned by the company
- Intangible assets: things like patents, copyrights, a company’s reputation, and other assets representing potential revenue
an org should keep track of intangible assets, like intellectual property, patents, trademarks, and company’s reputation, and copyrights to protect them
note: patents in the US are valid for 20 years

##### Asset management

Asset management refers to managing both tangible and intangible assets; this starts with inventories of assets, tracking the assets, and taking additional steps to protect them throughout their lifetime
* Accountability: ensures that account management has assurance that only authorized users are accessing a system and using it properly
  
* Hardware assets: IT resources such as computers, servers, routers, switches and peripherals
use an automated configuration management system (CMS) to help with hardware asset management
use barcodes, RFID tags to track hardware assets

* Software assets: operating systems and applications
important to monitor license compliance to avoid legal issues

### Data Roles (i.e., owners, controllers, custodians, processors, users/subjects)

* System owner: controls the computer storing the data; usually includes software and hardware configurations and support services (e.g. cloud implementation)
  
* data owner is the person respsonible for classifying, categorizing, and permitting access to the data; the data owner is the person who is best familiar with the importance of the data to the business system owners are responsible for the systems that process the data system owner is responsible for system operation and maintenance, and associated updating/patching as well as related procurement activities per NIST SP 800-18, information system owner has the following responsibilities:

** develops the system security plan
** maintains the system security plan and ensures that the system is deployed/operated according to security requirements
** ensures that system users and support personnel receive the requisite security training
** updates the system security plan as required
** assists in the identification, implementation, and assessment of the common security controls

* Data controller: decide what data to process and how to process it
the data controller is the person or entity that controls the processing of the data - deciding what data to process, why this data should be processed, and how it is processed
e.g. a company that collects personal information on employees for payroll is a data controller (but, if they pass this info to a third-party to process payroll, the payroll company is the data processor, see below)

* Data processor: an entity working on behalf (or the direction) of the data controller, that processes PII; they have a responsibility to protect the privacy of the data and not use it for any purpose other than directed by the data controller; generally, a data processor is any system used to process data
a controller can hire a third party to process data, and in this context, the third party is the data processor; data processors are often third-party entities that process data for an org at the direction of the data controller note GDPR definition: "a natural or legal person, public authority, agency, or other body, which processes personal data soley on behalf of the data controller"

* Data custodian: a custodian is delegated, from the system owner, day-to-day responsibilities for properly storing and protecting data; responsible for the protection of data through maintenance activities, backing up and archiving, and preventing the loss or corruption and recovering data
  
* Security administrator: responsible for ensuring the overall security of entire infrastructure; they perform tasks that lead to the discovery of vulnerabilities, monitor network traffic and configure tools to protect the network (like firewalls and antivirus software)
security admins also devise security policies, plans for business continuity and disaster recovery and train staff

* Supervisors: responsible for overseeing the activities of all the above entities and all support personnel; they ensure team activities are conducted smoothly and that personnel is properly skilled for the tasks assigned
Users: any person who accesses data from a computer device or system to accomplish work (think of users as employees or end users)

* users should have access to the data they need to perform tasks; users should have access to data according to their roles and their need to access info must comply with rules, mandatory policies, standards and procedures






