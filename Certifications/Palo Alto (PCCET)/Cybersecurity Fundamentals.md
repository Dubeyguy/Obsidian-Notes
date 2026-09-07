[[Network Security]]
[[Cloud Security]]
# Service Models
- There are three cloud computing service models
## Software as a Service ( SaaS )
- The capability provided to the consumer is to use the provider's applications running on a cloud infrastructure
- The consumer does not manage or control the underlying infrastructure, including the networks, servers, OS, storage or even individual application capabilities
- Example: Google, Microsoft, Zoom, Shopify, etc
- Use cases are human resource software management, Mobile app development, communication and office software, tec
## Platform as a Service ( PaaS )
- The capability provided to the consumer is to deploy onto cloud infrastructure consumer-created or acquired applications created using programming
- The consumer does not manage or control the underlying cloud infrastructure including network, servers, OS or storage but does control the deployed applications 
- Example: AWS, Oracle Cloud, Azure, etc
- Use cases are application deployment, auto scaling and clustering, CI/CD automation, container orchestration, etc
## Infrastructure as a Service ( IaaS )
- The capability provided to the consumer is to provision processing, storage, networks and other fundamental computing resources where the consumer is able to deploy and run arbitrary software 
- The consumer does not manage or control the underlying cloud infrastructure but does control the OS. networks, storage and deployed applications
- Example: AWS, IBM Cloud, Azure, etc
- Use cases are containers, virtual machines, network, storage, etc
### SaaS Security Challenges
- Malicious outsiders: Outside attackers using malware and other techniques
- Malicious insiders: Inside people trying to sabotage the organization
- Accidental data exposure: Exposing data accidentally
- Accidental share: Sharing to wrong people by accident
- Promiscuous share: A legitimate share is created for a user but the user shares it to someone else who shouldn't have access to it
- Ghost share: Share remains active for an employee or vendor that is no longer working with the company
# Standards and Regulations
## Payment Card Industry's Data Security Standard
- PCIDSS establishes its own cybersecurity standards and best practices for businesses and organizations that allow payment card purchases 
## European Union General Data Protection Regulations
- The EU's GDPR apply to any organization that does business with EU citizens 
- GDPR regulations often apply more stringent standards for end user and data protection than those that are applied domestically
# Attacker Profiles and Cyberattack Lifecycle
## Attacker Profiles
### Cybercriminals
- Most common attacker profile
- Known for ransomware, proliferation of bots and botnet attacks
### State-Affiliated Groups
- Sponsored by the government of a nation
- Acts against other country's infrastructure, governments, voting systems or major corporations
### Hacktivists
- Activists who make use of hacking to spread their influence and cause
- They perform high profile attacks to showcase their political or social cause
### Cyberterrorists
- Cyberterrorist attacks are often associated with state affiliations and often for causing damage and destruction
- attacks against power grids or public infrastructure
### Script Kiddies
- Novices who only rely on tools and don't understand the underlying functionality or the implications of their actions
### Cybercrime Vendors
- They rent or sell their malware and exploits like Business Email Compromise ( BEC ) and ransomware as Cybercrime as a Service ( CCaas ) offerings on the dark web
- They earn profit on selling or renting services and also commissions from the attackers
## Cyberattack Lifecycle
### Reconnaissance
#### Attack
- It includes researching, identifying and selecting targets, often extracting public information from targeted employee's social media platforms or from corporate websites
- Also use tools for scanning vulnerabilities, services and applications such as network analyzers, network vulnerability scanner, port scanner, password crackers, etc
#### Defense
- To defend against recon, requires effective end user security awareness training that focuses on social engineering techniques, social media and organizational security policies
- Continuous monitoring and inspection of network traffic flow to detect unauthorized port and vulnerability scans and other suspicious activities
### Weaponization
#### Attack
- Determination of methods to use to compromise a target endpoint
- Embedding intruder code withing PDF or word document or emails
#### Defense
- Challenging to intercept and stop weaponization because it occurs in the attacker's network
- Preventive measures can be taken to defend against the next step
### Delivery
#### Attack
- Delivering the weaponized payload to the target endpoint via email, IM, drive-by download or infected file share
#### Defense
- Requires visibility into all network traffic ( including remote and mobile devices ) to block malicious websites, applications and IP addresses to prevent known and unknown malware and exploits
### Exploitation
#### Attack
- Triggering the delivered payload
- Maybe triggered by the end user by clicking a link or opening an infected attachment, etc or by triggered remotely by the attacker
#### Defense
- Effective end user security awareness on malware protection and email security
- Vulnerability and patch management
- malware detection and prevention
- Threat intelligence; blocking risky, unauthorized or unneeded applications and services
- Managing file or directory permissions and root privileges
- Logging and monitoring network activity
### Installation
#### Attack
- Escalating privileges by establishing remote shell access and installing rootkits or other malware
- Establishing persistence by compromising additional endpoints
#### Defense
- Limit or restrict the attackers' lateral movement within the network
- Using network segmentation and zero trust model
### Command and Control
#### Attack
- Attackers establish encrypted communication channel back to command-and-control  ( C2 ) servers across the internet to modify attack objectives or to evade the countermeasures 
- Attack communication traffic is usually hidden with various techniques and tools like encryption, circumvention, port evasion, fast flux ( Dynamic DNS ) and DNS tunneling
#### Defense
- Inspecting all network traffic whether it is encrypted or not
- Blocking outbound C2 communications with anti-C2 signatures
- Blocking all outbound communications to known malicious URLs and IP addresses
- Blocking novel attack techniques that employ port evasion methods
- Preventing use of anonymizers and proxies on the network
- Monitoring DNS for malicious domains and countering with DNS sinkholing or DNS poisoning
- Redirecting malicious outbound communications to honeypots 
### Act on Objective
#### Attack
- Data theft
- Destruction or modification of critical systems, networks and data
- Denial-of-Service attacks ( DoS )
#### Defense
- Monitoring and awareness
## High Profile Cyberattacks
### Solarwinds ( December 2020 )
- Attack using malware in Solarwinds Orion network software update 
- Perpetrated by the APT29 ( Cozy Bear / Russian SVR ) threat group
- One of the most damaging supply chain attacks in history ( more than 300,000 customers affected) including the U.S. Federal government and 425 of Fortune 500 companies
### Colonial Pipeline ( May 2021 )
- Colonial pipeline company was hit by Ransomware as a Service ( RaaS ) attack
- Perpetrated by the DarkSide threat actor
- Paid $4.4 million ransom
### JBS S.A. ( May 2021 )
- JBS S.A. ( largest beef, chicken and pork producer ) was hit by a ransomware attack
- Perpetrated by the REvil group
- Paid $11 million ransom
## MITRE ATT&CK Framework
- MITRE Adversarial Tactics, Techniques and Common knowledge framework is a comprehensive matrix of techniques designed for threat hunters, defenders and red teams to help classify attacks, identify attack attribution and objective, and assess an organization's risk
- ATT&CK for Enterprise: Focuses on adversarial behavior in Windows, Mac, Linux and cloud environments
- ATT&CK for Mobile: Focuses on IOS and Android
# Malware Types and Advanced Malware
- Stands for malicious software
- A file or code that typically takes control of, collects information from, or damages an infected endpoint
## Malware Types
### Logic Bombs
- Triggered by a specified condition such as a date or a particular user account being disabled
### Spyware and Adware
- Collects information such as internet surfing behavior, login credentials and financial account information
### Rootkits
- Provides privileged ( root level ) access to a computer
- Installed on BIOS of the machine
### Bootkits
- kernel mode variant of rootkits
- Used to attack computers with full disk encryption
### Backdoor
-  Allows an attacker to bypass authentication and gain access to a compromised system
### Anti-AV
- Disassembles legitimately installed antivirus software on the compromised endpoint
- Preventing automatic detection and removal of other malware
### Ransomware
- Locks a computer or encrypts data on an infected endpoint
- Example of locker ransomware: Reveton and LockeR
- Example of crypto ransomware: Locky, TeslaCrypt/EccKrypt, Cryptolocker, Cryptowall, etc
### Trojan Horses
- Appears harmless but gives the attacker complete control over the infected endpoint
- Can't self-replicate
### Virus
- It is self-replicating
- Must infect a host program and be executed by a user or process
### Worms
- Targets a computer network by replicating itself 
- Unlike viruses, they do not need to infect other programs or be executed 
## Characteristics of Advanced Malware
### Obfuscation
- Uses obfuscation techniques to hide certain binary strings that are characteristically used in malware to evade anti-malware software
- Might also hide an entire malware program
### Polymorphism
- Code that keeps changing the signature of the malware and thus infinite signature hashes
- Techniques like polymorphism and metamorphism are used to avoid detection by anti-malware tools
### Distributed
- Can have multiple control servers all over the globe with multiple fallback options
- Can also leverage other infected endpoints as communication channels
### Multi-functional
- Enables an attacker to use endpoints strategically to accomplish specific task such as stealing credit card info, sending spam, etc
# Cyberattack Techniques
## Business Email Compromise
- Most prevalent type of attack nowadays faced by organizations
- Second most common form of social engineering
## Phishing
### Spear Phishing
- Targeted according to the victim's information
- More success rate than general phishing
### Whaling
- A type of spear phishing attack
- Directed at senior executives or other high profile targets within an organization
### Watering Hole
- Compromises websites that are likely to be visited by a targeted victim
- Infects unsuspecting visitors with malware ( drive-by download)
### Pharming
- Redirects legitimate website's traffic to a fake site
- By modifying endpoint's local hosts file or compromising a DNS server
## Bots and Botnets
- very difficult for organizations to detect
### Bots
- Bots ( or zombies ) are individual endpoints that are infected with advanced malware
### Botnets
- Network of bots working together under the  attacker's control
- Example: Rustock Botnet could send up to 25000 spam email per hour from an individual bot. it had infected almost 2.4 million devices. In March 2011, FBI working with Microsoft and others took down Rustock. By then it was responsible for 60% of world's spam
# Advanced Persistent Threats ( APTs ) and Wi-Fi Vulnerabilities
- Advanced: Attackers use advanced malware and exploits
- Persistent: An APT may take place over a period of several years
- Threat: An APT is more deliberate and focused, rather than opportunistic. They are designed to cause real damage
- Example: The **Lazarus** group is known as an APT, also known as Bluenoroff and Hidden Cobra. Initially known for launching attacks against government of South Korea and Asia, recently targeting banks, casinos, financial investment software developers and crypto currency businesses
## Wi-Fi challenges

