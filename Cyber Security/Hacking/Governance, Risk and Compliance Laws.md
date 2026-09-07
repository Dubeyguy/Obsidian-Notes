# Regulatory Compliance Considerations

- **PCI DSS**: The Payment Card Industry Data Security Standard (PCI DSS) regulation aims to secure the processing of credit card payments and other types of digital payments. PCI DSS specifications, documentation, and resources can be accessed at [_https://www.pcisecuritystandards.org_](https://www.pcisecuritystandards.org/).
- **HIPAA**: The original intent of the Health Insurance Portability and Accountability Act of 1996 (HIPAA) regulation was to simplify and standardize healthcare administrative processes. Administrative simplification called for the transition from paper records and transactions to electronic records and transactions. The U.S. Department of Health and Human Services (HHS) was instructed to develop and publish standards to protect an individual’s electronic health information while permitting appropriate access and use of that information by healthcare providers and other entities. Information about HIPAA can be obtained from [_https://www.cdc.gov/phlp/publications/topic/hipaa.html_](https://www.cdc.gov/phlp/publications/topic/hipaa.html).
- **FedRAMP**: The U.S. federal government uses the Federal Risk and Authorization Management Program (FedRAMP) standard to authorize the use of cloud service offerings. You can obtain information about FedRAMP at [_https://www.fedramp.gov_](https://www.fedramp.gov/).
- **General Data Protection Regulation (GDPR)**:  GDPR includes strict rules around the processing of data and privacy. One of the GDPR’s main goals is to strengthen and unify data protection for individuals within the European Union (EU), while addressing the export of personal data outside the EU. In short, the primary objective of the GDPR is to give citizens control of their personal data. You can obtain additional information about GDPR at [_https://gdpr-info.eu_](https://gdpr-info.eu/).

# Regulations

**Regulations in the Financial Sector**

Financial services institutions such as banks, credit unions, and lending institutions provide an array of solutions and financial instruments. You might think that money is their most valuable asset, but in reality, customer and transactional information is the heart of their business. Financial assets are material and can be replaced. Protection of customer information is necessary to establish and maintain trust between a financial institution and the community it serves. More specifically, institutions have a responsibility to safeguard the privacy of individual consumers and protect them from harm, including fraud and identity theft. On a broader scale, the industry is responsible for maintaining the critical infrastructure of the nation’s financial services.

The following are a few examples of regulations applicable to the financial sector:

- Title V, Section 501(b) of the Gramm-Leach-Bliley Act (GLBA) and the corresponding interagency guidelines
- The Federal Financial Institutions Examination Council (FFIEC)
- The Federal Deposit Insurance Corporation (FDIC) Safeguards Act and Financial Institutions Letters (FILs)
- The New York Department of Financial Services Cybersecurity Regulation (NY DFS Cybersecurity Regulation; 23 NYCRR Part 500)

Compliance with some regulations, such as NYCRR and GLBA, is mandatory.

GLBA defines a _financial institution_ as “any institution the business of which is significantly engaged in financial activities as described in _Section 4(k) of the Bank Holding Company Act_ (12 U.S.C. § 1843(k))”. GLBA applies to all financial services organizations, regardless of size. This definition is important to understand because these financial institutions include many companies that are not traditionally considered to be financial institutions, including the following:

- Check-cashing businesses
- Payday lenders
- Mortgage brokers
- Nonbank lenders (for example, automobile dealers providing financial services)
- Technology vendors providing loans to clients
- Educational institutions providing financial aid
- Debt collectors
- Real estate settlement service providers
- Personal property or real estate appraisers
- Retailers that issue branded credit cards
- Professional tax preparers
- Courier services

The law also applies to companies that receive information about customers of other financial institutions, including credit reporting agencies and ATM operators.

The Federal Trade Commission (FTC) is responsible for enforcing GLBA as it pertains to financial firms that are not covered by federal banking agencies, the Securities and Exchange Commission (SEC), the Commodity Futures Trading Commission (CFTC), and state insurance authorities, which include tax preparers, debt collectors, loan brokers, real estate appraisers, and nonbank mortgage lenders. GLBA mandates that financial organizations undergo periodic penetration testing in their infrastructure. Additional information about the GLBA can be obtained at [_https://www.ftc.gov/tips-advice/business-center/privacy-and-security/gramm-leach-bliley-act_](https://www.ftc.gov/tips-advice/business-center/privacy-and-security/gramm-leach-bliley-act).

Another example is the NY DFS Cybersecurity Regulation. Section 500.05 of this regulation requires the covered entity to perform security penetration testing and vulnerability assessments on an ongoing basis. The cybersecurity program needs to include monitoring and testing, developed in accordance with the covered entity’s risk assessment, which is designed to assess the effectiveness of the covered entity’s cybersecurity program. The regulation dictates that “the monitoring and testing shall include continuous monitoring or periodic penetration testing and vulnerability assessments.” The organization must conduct an annual security penetration testing and a biannual vulnerability assessment. The NY DFS Cybersecurity Regulation can be accessed at [_https://www.dfs.ny.gov/industry_guidance/cyber_faqs_](https://www.dfs.ny.gov/industry_guidance/cyber_faqs).

**Regulations in the Healthcare Sector**

On February 20, 2003, the Security Standards for the Protection of Electronic Protected Health Information, known as the HIPAA Security Rule, was published. The Security Rule requires technical and nontechnical safeguards to protect electronic health information. The corresponding HIPAA Security Enforcement Final Rule was issued on February 16, 2006. Since then, the following legislation has modified and expanded the scope and requirements of the Security Rule:

- The 2009 Health Information Technology for Economic and Clinical Health Act (known as the HITECH Act)
- The 2009 Breach Notification Rule
- The 2013 Modifications to the HIPAA Privacy, Security, Enforcement, and Breach Notification Rules under the HITECH Act and the Genetic Information Nondiscrimination Act; Other Modifications to the HIPAA Rules (known as the Omnibus Rule)

HHS has published additional cybersecurity guidance to help healthcare professionals defend against security vulnerabilities, ransomware, and modern cybersecurity threats. See [_https://www.hhs.gov/hipaa/for-professionals/security/guidance/ cybersecurity/index.html_](https://www.hhs.gov/hipaa/for-professionals/security/guidance/).

The HIPAA Security Rule focuses on safeguarding electronic protected health information (ePHI), which is defined as individually identifiable health information (IIHI) that is stored, processed, or transmitted electronically. The HIPAA Security Rule applies to covered entities and business associates. Covered entities include healthcare providers, health plans, healthcare clearinghouses, and certain business associates. Select each covered entity for more information.

HHS has published HIPAA Security Rule guidance material at [_https://www.hhs.gov/hipaa/for-professionals/security/guidance/index.html_](https://www.hhs.gov/hipaa/for-professionals/security/guidance/index.html).

**Payment Card Industry Data Security Standard (PCI DSS)**

In order to protect cardholders against misuse of their personal information and to minimize payment card channel losses, the major payment card brands (Visa, MasterCard, Discover, and American Express) formed the Payment Card Industry Security Standards Council (PCI SSC) and developed the Payment Card Industry Data Security Standard (PCI DSS). The latest version of the standard and collateral documentation can be obtained at [_https://www.pcisecuritystandards.org_](https://www.pcisecuritystandards.org/).

PCI DSS must be adopted by any organization that transmits, processes, or stores payment card data or that directly or indirectly affects the security of cardholder data. Any organization that leverages a third party to manage cardholder data has the full responsibility of ensuring that this third party is compliant with PCI DSS. The payment card brands can levy fines and penalties against organizations that do not comply with the requirements and/or can revoke their authorization to accept payment cards.

Before we proceed with details about how to protect cardholder data and guidance on how to perform penetration testing in PCI environments, we must define several key terms that are used in this module and are defined by the PCI SSC at [_https://www.pcisecuritystandards.org/documents/PCI_DSS_Glossary_v3-2.pdf_](https://www.pcisecuritystandards.org/documents/PCI_DSS_Glossary_v3-2.pdf). Select each of the following terms for a definition.

