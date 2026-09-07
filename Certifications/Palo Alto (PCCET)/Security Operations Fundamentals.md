[[Cloud Security]]
[[Cybersecurity Fundamentals]]
[[Network Security]]

# Security Operations
## Elements of SecOps
- Processes
- Interfaces
- People
- Business
- Visibility
- Technology
## Functions
- Identify: Identify an alert as potentially malicious and open an incident
- Investigate: Investigate the root cause and impact of the incident
- Mitigate: Stop the attack
- Continuously improve: Adjust and improve the operations to stay current with changing and emerging threats
# Security Orchestration
- Method of connecting disparate security technologies through standardized and automatable workflows that enables security teams to carry out incident response and operations
## Terminology
- Security Automation: Process of executing tasks using machine-driven responses to help ensure consistency in security issues
- Playbooks: Task based graphical workflows that help visualize processes across security products
- Integration: A mechanism through which security orchestration technologies communicate with other products using REST APIs, webhooks, etc
- Ingestion: Process through which security orchestration tools consume alerts from other security products
## Tools and Technologies
- SIEM: Software Information and Event Management monitors multiple sources to collect, correlate and aggregate data providing reports, alerts and information for real time detection and mitigation
- Threat Intelligence: Collects and correlates data from both internal and external sources to provide information to determine malicious intent
- Endpoint Security: Provides real time protection for devices such as mobile phones, laptops and desktop systems connected to the enterprise network
- Network Security: Hardware and software components that provide protection for the enterprise network infrastructure
# Business Pillar
- It defines the purpose of the SecOps team to the business and how it will be managed
## Elements
- Mission: What are we doing
- Governance: How are we going to manage what we are doing
- Planning: How are we going to do it
- Budget: What will it cost to do this
- Staffing: Who do we need to do this
- Facility: Where are we going to do this
- Metrics: How do we know it's working efficiently
- Reporting: How will we track activity and provide updates
- Collaboration: How will we communicate and track issues with the rest of the business
## Metrics
### Poor Metrics
- Mean Time to Resolution ( MTTR ): MTTR is a good metric when used in a Network Operations Centre ( where uptime is the key) but it can be detrimental when used in SecOps. Holding analysts accountable for MTTR will result in rushed and incomplete analyses
- Number of Incidents Handled: Ranking top performers by number of incidents handled can have skewed results and may lead to analysts " cherry-picking" incidents that are faster and easier to resolve, it also violates laws in various countries
- Number of Firewalls Rules Deployed: Counting the number of firewall rules deployed can be a poor metric because 10.000 firewall rules can be in place but if the first rule is ' any-any ' then the rest are useless
- Number of Feeds into SIEM: It is similar to counting number of firewall rules deployed. If there are 15 data feeds but only one use-case, then the data feeds aren't being utilized and are a potentially expensive waste
### Good Metrics
- Good metrics should provide insight into whether the business should have confidence or not. 
- There are two type of confidence to focus on:
#### Configuration Confidence
- It is knowing that your technology is configured to prevent an attack that can be remediated or analyzed
- Are the security controls running
- How many changes are occurring outside of the change control policy
- Are the technologies in place configured to best practices
- What percentage of features and capabilities are being utilized
#### Operational Confidence
- It is knowing that the right people and processes are in place to handle a breach if/when it occurs
- How many events are analysts handling per hour ( EPAH )
- Are there repeated incidents flowing into the SecOps 
- Is the SecOps handling alerts for known threats
- How often are there deviations in SecOps procedures
## Reporting
- Reporting is meant to give an account of what has been observed, done, heard and investigated
- Daily Reports: Daily reports should include open incidents with details centered on daily activity
- Weekly Reports: Should identify security trends to initiate threat-hunting activities which include the number of cases opened and closed, conclusions of the tickets, how many different security use cases were triggered and their severity, and how were they distributed through hours of the day
- Monthly Reports: Should focus on the overall effectiveness of the SecOps function. They should cover topics such as how long events are sitting in the queue before being triaged, if the staffing the the SOC is appropriate, what is the efficiency of rule fires and are their rules that never fire or always fire a false positive
# People Pillar
- The People pillar defines who will be accomplishing the goals of the SecOps team and how they will be managed
## Elements
- Employee Utilization: How will we manage the workload
- Training: How will we find staff and train them to fulfill their roles
- Career Path Progression: What will we do to retain staff
- Tabletop Exercises: How will we validate staff actions for efficacy
## Employee Utilization
-  Tasks to prevent employee burnout
  - Shift turnover stand-up meeting ( beginning of shift )
  - Event triage
  - Incident response
  - Project work
  - Training
  - Reporting
  - Shift turnover stand-up meeting ( end of shift )
## Training
- Types of training content
  - Company security and privacy training
  - Tool-feature use
  - Process documentation and execution
  - Communication plans
  - Continuous education
## Career Path Progression
- A role's definition and skill matrix should be created
- Details of job roles and levels in each path should be documented and shared with the team
- Education opportunities should be provided to the staff to help them move through their preferred career path
## Tabletop Exercises
- Planned events where the stakeholders for the SecOps or the entire security organization walk through a security event to test the processes and reactions to the type of incident
# Processes Pillar
- It defines the step by step instructions and functions that are to be carried out by the SecOps team for the necessary security policies to be followed
## Elements
### Identification
- Alerting
- Initial Research
- Severity Triage
- Escalation Process
### Investigation
- Detailed Analysis
### Mitigation
- Breach Response
- Mitigation
- Pre Approved Mitigation Scenarios
- Interface Agreements
- Change Control
### Continuous Improvement
- Tuning
- Process Improvement
- Capability Improvement
- Quality Review
# Interfaces Pillar
- Each interaction with another team is defined as an interface
- The interfaces pillar defines which functions need to take place to help achieve the stated goals, and how the SecOps will interface with other teams within the organization by identifying the scope of each team's responsibilities and the separation of each team's duties
## Elements
### Element 1
- Help Desk: Close tickets quickly
- IT Operations: Availability and performance of IT infrastructure
- DevOps: Develop, implement and maintain applications; release bug-free features quickly
### Element 2
- Operational Technology Team : Manage and maintain OT, IoT and IIoT systems
- Enterprise Architecture: Meet business network requirements
- SOC Engineering: implement and maintain SecOps tools
### Element 3
- Endpoint Security Team: Secure the endpoint
- Network Security Team: Secure the network
- Cloud Security Team: Secure the cloud
### Element 4
- Threat Hunting: Identify high-fidelity threats
- Content Engineering: Create useful alerting profiles
- Security Automation: Speed response to security issues
### Element 5
- Forensics and Telemetry: Collect court-admissible evidence about breaches
- Threat intelligence Team: Identify potential risks
- Red and Purple Team: Mimic adversaries to breach the organization
### Element 6
- Governance, Risk and Compliance: Create guideline to meet business and compliance requirements
- Business Liaison: Prepare the security organization to support changing business needs
- Vulnerability Management Team: Patch systems quickly
# Visibility Pillar
- It enables SecOps team to use tools and technology to capture network traffic, limit access to certain URLs, determine which applications are being used by end users and to detect and prevent accidental or malicious release of proprietary or sensitive information
## Elements
- Network Traffic Capture
- Endpoint Data Capture
- Cloud Computing
- Application Monitoring
- URL Filtering
- SSL Decryption
- Threat intelligence Platform
- Vulnerability Management Tools
- Analysis Tool
- Asset Management
- Knowledge Management
- Case Management
- Data Loss Prevention
# Technology Pillar
- It includes tools and technology to increase our capabilities to prevent or greatly minimize attempts to infiltrate your network
## Elements
- Firewall
- IPS/IDS
- Malware Sandbox
- Endpoint Security
- Behavioral analytics
- Email Security
- Network Access Control
- IAM
- Honey Pots and Deception
- Web Application Firewall
- VPN
- Mobile Device Management
- Security Information and Event Management ( SIEM )
- Security Orchestration Automation Response ( SOAR )
# SOAR Technology
## Common SOAR playbooks
- Phishing Enrichment and Response
- Threat Hunting
- IoC Enrichment
- Incident Severity Assessment
- Cloud Security Orchestration