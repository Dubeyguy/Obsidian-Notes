[[Network Security]]
[[Cybersecurity Fundamentals]]
# Virtualization, Containers and Micro-VMs
- The Cloud Native Computing Foundation's ( CNCF ) charter defines three properties of cloud native technologies
   1) Container Packaged: Running applications and processes in software containers as isolated units of application deployment, and as mechanisms to achieve high levels of resource isolation. Improves overall developer experience, fosters code and component reuse and simplifies operations for cloud native applications
   2) Dynamically Managed: Actively scheduled and managed by a central orchestrating process. Radically improves machine efficiency and resource utilization while reducing maintenance costs
   3) Micro-serviced: Loosely coupled with dependencies explicitly described. Significantly increases the overall agility and maintainability of the applications
## Important Terminology
- Hypervisor: It allows multiple, virtual operating systems to run concurrently on a single physical host or computer
- Native: A native ( also known as type 1 or bare metal ) hypervisor runs directly on the host computer's hardware
- Hosted: A hosted ( type 2 ) hypervisor runs within an operating system environment
## Containers
- Package of software that allows applications to run independently within a host operating system
---
# Serverless Technology
## Serverless Computing and Function as a Service ( FaaS )
- They enable organizations to build and deploy software and services without maintaining or provisioning any physical or virtual servers
## Advantages
- Focus on core product functionality
- Not responsible for security patches
- Secure data center, network and servers
## Disadvantages
- Increased attack surface
- Attack surface complexity
- Overall system complexity
- Inadequate security testing
---
# Application Development Platforms and Processes
## Cloud Native Security Platform
- It contains scalability, deployability, manageability and limitless on demand compute power and applies these principles to software development, combined with CI/CD automation to increase productivity, business agility and cost savings 
### Continuous Integration / Continuous Delivery ( CI/CD )
- Application development models are moving away from traditional waterfall model towards more agile Continuous Integration / Continuous Delivery processes with end-to-end automation
#### Benefits
- Shorter time to market
- Efficient software delivery
#### Challenges
- Limited prevention control
- Poor visibility
- Tools with lack of automation
## Cloud Native Architectures
- Cloud native architectures consists of cloud services such as containers, serverless security, PaaS and microservices
- These services are loosely coupled which means they are not hardwired to any infrastructure components, thus allowing the developers to make changes frequently without affecting other pieces of the application
## DevOps
- Collaboration between development teams and IT operations
- DevOps teams have a closer relationship with the development teams in order to facilitate the release of applications
## SecOps
- Essentially It operations team with a focus on security
- SecOps teams directly integrate security into the IT operations
## DevSecOps
- More focus on ensuring security than DevOps and SecOps teams
- They focus on applying application and infrastructure security automation and processes across the CI/CD pipeline
## CNSP Functionality
- Visibility: Provides unified visibility for SecOps and DevOps teams
- Integration: Deliver and integrated set of capabilities to respond to threats and protect cloud-native applications
- Automation: Automate the remediation of vulnerabilities and misconfigurations consistently across the entire build-deploy-run lifecycle
## DevOps Software Development Model
- The DevOps Software Development Model is enhancing or replacing the traditional Software Development Life Cycle ( SDLC ) model
- In the SDLC model, developers write large amount of code for new features, products, bug fixes and then pass it to the operations team to test and release it which could take months
- DevOps unites the development and operations team throughout the entire software delivery process, enabling them to discover and remediate issue earlier
### Characteristics
- Collaborative Teams: Two separate teams operate in a communicative and collaborative way
- Culture: DevOps refers to a culture where developers, testers and operations personnel cooperate through the entire software delivery lifecycle
- More than automation: Although automation is very important for DevOps culture, automation alone doesn't define DevOps
## DevOps CI/CD Pipeline
- DevOps is a cycle of continuous integration and continuous delivery
- The CI/CD pipeline integrates the development and operations teams to improve productivity by automating infrastructure and workflows
- Continuous Integration ( CI ): It requires developers to integrate code into a repository several times per day for automated testing
- Continuous Delivery ( CD ): It means that the CI pipeline is automated but the code must go through manual technical checks before it is implemented for production
- Continuous Deployment: It takes CD one step further. Instead of requiring manual checks, the code passes automated testing and is automatically deployed, giving customers instant access to new features
---
# Security Operations Responsibilities
## IAM Security
- It is part of the larger Cloud Infrastructure Entitlement Management ( CIEM )
- Focuses on detecting gaps between privileges that are required and privileges that are unneeded
## Principle of Least Privilege
- Users are given minimum privileges that are needed to accomplish their task
---
# Cloud Native Application Protection
## Cloud Native Application Protection Platform ( CNAPP )
- A unified and tightly integrated set of security and compliance capabilities designed to secure and protect cloud native applications across development and production
- They consolidate a large number of previously siloed capabilities including container scanning, cloud security posture management infrastructure as code scanning, CIEM, runtime cloud workload protection and runtime vulnerability/configuration scanning
## Cloud Native Computing Foundation
- CNCF is a Linux OS foundation project founded in 2015 to help advance container technology and align the tech industry around its evolution
## Distributed Cloud
- Execution environment where application components are placed at appropriate geographically dispersed locations chosen to meet the requirements of the application
## CSPM - Visibility, Governance, and Compliance
### Compliance Requirements
- Real time discovery and classification of resources and data across dynamic SaaS as well as PaaS and IaaS environments
- Ensuring application and resource configurations match your security best practices as soon as they are deployed
- Using granular policy definitions to govern access to SaaS applications and resource in the public cloud and to apply network segmentation
- Leveraging automation and built in compliance frameworks to ensure compliance at any time, including the generation of audit ready reports on demand
- Having a seamless UX means additional steps are not forced and do not introduce significant latency in the use of applications as you add new security tools
## Cloud Workload Protection
- Provides consistent visibility and control, including vulnerabilities scanning in the development process, workload protection at runtime, application control, memory protection, behavioral monitoring, host based intrusion prevention and optional anti malware protection
## CIEM
- Process of managing identities and privileges in cloud environments
- Understand which access entitlements exist across cloud and multi-cloud environments and then identify and mitigate risks resulting from entitlements that grant higher level of access than they should
- Principle of least privilege is used
