## Types of SOC Models

Depending on your security needs and budget, there are several types of SOC

![](https://app-ld-img.s3.us-east-2.amazonaws.com/training/soc-models.png)

### In-house SOC

This team is formed when an organization builds its cybersecurity team. Organizations considering an internal SOC should have a budget to support its continuity.

### Virtual SOC

This type of SOC team does not have a permanent facility and often works remotely in various locations.

### Co-Managed SOC

The Co-Managed SOC consists of internal SOC staff working with an external Managed Security Service Provider (MSSP). Coordination is key in this type of model.

### Command SOC

This SOC team oversees smaller SOCs across a large region. Organizations using this model include large telecommunications providers and defense agencies.

---

## SOC Roles


### SOC Analyst

This role can be categorized as Level 1, 2, and 3 according to the SOC structure. A security analyst classifies the alert, looks for the cause, and advises on remediation.

### Incident Responder

An Incident Response Officer is an individual responsible for threat detection. This role performs the initial assessment of security breaches.

### Threat Hunter

A Threat Hunter is a cybersecurity professional who proactively seeks out and investigates potential threats and vulnerabilities within an organization's network or system. They use a combination of manual and automated techniques to detect, isolate, and mitigate advanced persistent threats (APTs) and other sophisticated attacks that may evade traditional security measures. Threat hunters typically have a deep understanding of the organization's IT infrastructure and security posture, as well as knowledge of emerging threats and attack tactics. They aim to find and eliminate threats before they can damage or disrupt the business.

### Security Engineer

Security engineers are responsible for maintaining the security infrastructure of Security Information and Event Management (SIEM) solutions and security operations center (SOC) products. For example, a security engineer builds the connection between SIEM and Security Orchestration, Automation, and Response (SOAR) products.

### SOC Manager

A SOC manager takes on management responsibilities such as budgeting, strategizing, managing staff, and coordinating operations. They deal with operational rather than technical issues.

---

## A Day in the Life of a SOC Analyst

Throughout the day, a SOC analyst typically reviews alerts in the SIEM and determines which ones are real threats. To reach a conclusion, they use various security and protection products such as Endpoint Detection and Response (EDR), Log Management, and SOAR. We will explain in detail why and how these products are used later in the training program.

To be a successful SOC analyst who is not dependent on security products and can correctly analyze SIEM alerts, you must have the following skills and abilities.

### Operating Systems

To determine what is abnormal in a system, you first need to know what is accepted as normal. For example, there are many services within the Windows operating system, and it is difficult to know which ones are suspicious without knowing which ones are or could be considered normal Windows services. Therefore, you should be familiar with how Windows/Linux operating systems work.

### Network

First and foremost, in this role, you will be dealing with a lot of malicious IPs and URLs, so you need to confirm that there are no devices on the network trying to connect to those addresses. Once you accomplish that, it will set the direction of the analysis.

This step is a bit more complicated because you may have to find a potential data leak on the network. To perform all of these functions, you need to understand the basics of networking.

### Malware Analysis

When dealing with most threats, you are likely to encounter some type of malicious software. To understand the real purpose of these malicious programs (they sometimes display different behaviors to fool analysts), you need to have malware analysis skills.

It is important to at least determine what the command and control center of the malicious file is and whether or not there is a device communicating with that address.

---

## What is SIEM?

SIEM is a security solution that combines security information and event management, which involves real-time logging of events in an environment. The ultimate purpose of event logging is to detect security threats.

Overall, SIEM products have a lot of features. The ones that interest us most as SOC analysts are those that collect and filter data and provide alerts for suspicious events.

Example alert: If someone on a Windows operating system tries to enter 20 incorrect passwords in 10 seconds, this is suspicious activity. It is unlikely that someone who has forgotten their password would try to re-enter it that many times in such a short period of time. So we create a SIEM rule/filter to detect such activity that exceeds the threshold. Based on this SIEM rule, an alert will be generated when such a situation occurs.
  

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/SOC+Fundamentals/siem/siem+alert.png)

Some popular SIEM solutions: IBM QRadar, ArcSight ESM, FortiSIEM, Splunk, etc. To get a better picture, you can visit the “Monitoring” page on LetsDefend.

---

## What is EDR?

Endpoint Detection and Response (EDR), also known as Endpoint Threat Detection and Response (ETDR), is an integrated endpoint security solution that combines continuous, real-time monitoring and collection of endpoint data with rules-based automated response and analysis capabilities. (Definition source: mcafee.com)

## Analysis with EDR

Some EDR solutions commonly used in the workplace: CarbonBlack, SentinelOne, and FireEye HX.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/SOC+Fundamentals/edr/edr-letsdefend.PNG)

As you can see in the image, the accessible endpoint devices are listed on the left. You can search for endpoints in the search bar, or if there is an IOC (an IP address, file hash, process name, etc.), we can perform a search across all hosts.

The right side displays general information about the device and shows sections such as Browser History, Network Connections, and Process List.

---

### SOAR (Security Orchestration Automation and Response)

SOAR stands for Security Orchestration Automation and Response. It enables security products and tools in an environment to work together, streamlining the tasks of SOC team members. For example, it will automatically search VirusTotal for the source IP of a SIEM alert, reducing the workload of the SOC analyst.

Some SOAR products commonly used in the industry:

- Splunk Phantom
- IBM Resilient
- Logsign
- Demisto

The image below shows what can be achieved with a SOAR solution.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/SOC+Fundamentals/SOAR/soar-capabilities.jpg)

### Centralization (A single platform for everything you need)

It allows you to use different security tools in your environment (sandbox, log management, 3rd party tools, etc.) by providing an all-in-one software. These tools are integrated into the SOAR solution and can be used on the same platform.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/SOC+Fundamentals/SOAR/soar-central.PNG)

### Playbooks

You can easily investigate SIEM alerts using playbooks created for different scenarios within SOAR. Even if you don't know or remember all the procedures, you can perform an analysis by following the steps outlined in the playbooks

In addition, these playbooks help ensure that the entire SOC team is on the same page when performing their analysis. For example, all team members need to check IP reputation, so if one team member is not checking it and the others are, this is an undesirable situation. We can avoid this situation by adding this step to the playbook.

---

### Threat Intelligence Feed

A SOC team should be immediately aware of the latest threats and take the necessary precautions. To meet this need, threat intelligence feeds are created. As a SOC analyst, you can use these feeds to guide your investigations.

A Threat Intelligence Feed is data (such as malware hashes, C2 (Command&Control) domain/IP addresses etc.) provided by a third party company.

The data here consists of artifacts from previous malicious activity. It could be the hash of malware or the IP address of a command and control center. As a SOC analyst, you need to search threat intelligence feeds to determine if a hash file at hand has ever been used in a malicious scenario in the past.

Here are some free and popular sources you can use:

- [VirusTotal](https://www.virustotal.com/)
- [Talos Intelligence](https://talosintelligence.com/)

Important points to highlight:
### **If data you run through feeds does not show up**

Let's say you ran a hash of an .exe in VirusTotal and in the past you didn't find anything suspicious about it. In this case, you should not just assume that the file is clean, that would be a mistake. A SOC analyst should carefully perform the necessary file analysis (static/dynamic).

### **We shouldn’t forget that IP addresses can change hands.**

For example, let's say an attacker created a server on AWS (Amazon Web Services) and used it as a command and control center. Then various threat intelligence feeds listed that IP address as a malicious address.

2 months later, the attacker shut down the server and someone else moved their personal blog to that server. This doesn't mean that people who visited the blog were exposed to malicious content. The fact that this IP address has been used for malicious purposes in the past does not mean that it contains malicious content.

