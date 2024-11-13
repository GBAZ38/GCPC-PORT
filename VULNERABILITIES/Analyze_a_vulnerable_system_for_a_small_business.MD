# Scenario

You are a newly hired cybersecurity analyst for an e-commerce company. The company stores information on a remote database server, since many of the employees work remotely from locations all around the world. Employees of the company regularly query, or request, data from the server to find potential customers. The database has been open to the public since the company's launch three years ago. As a cybersecurity professional, you recognize that keeping the database server open to the public is a serious vulnerability.

You are tasked with completing a vulnerability assessment of the situation to communicate the potential risks to decision makers at the company. You must create a written report that explains how the vulnerable server is a risk to business operations and how it can be secured.

For this activity I will be using the Vulnerability assessment report template provided in the GCPC course.

I will also be referencing [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final)

---

# Vulnerability assessment report

## System Description

The server hardware consists of a powerful CPU processor and 128GB of memory. It runs on the latest version of Linux operating system and hosts a MySQL database management system. It is configured with a stable network connection using IPv4 addresses and interacts with other servers on the network. Security measures include SSL/TLS encrypted connections.

## Scope
The scope of this vulnerability assessment relates to the current access controls of the system. The assessment will cover a period of three months, from June 2025 to August 2025. [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final) is used to guide the risk analysis of the information system.

## Purpose
The purpose of this vulnerability assessment is to secure the database server by ensuring the system has proper access controls. The database server is valuable because of the information and data it contains. It is important to secure the data on the server in order to comply with regulatory standards, and ensure customer and employee data security. If the server were disabled it could cause loss of revenue, customer trust, and even regulatory penalties.

## Risk assessment

| Threat source      | Threat event                                                                                                                         | Likelihood | Severity | Risk |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------|------------|----------|------|
| Competitor         | Obtain sensitive information via exfiltration                                                                                        | 1          | 3        | 3    |
| Hacker/ Hacktivist | Obtain sensitive information via exfiltration/ interfere with business operation via intrusion/ Conduct "man-in-the-middle" attacks. | 2          | 3        | 6    |
| Customer           | Alter/Delete critical information                                                                                                    | 1          | 3        | 3    |

## Approach

Even in this limited example of potential threats there is a high risk potential to the database server. If a competitor was able to obtain and exfiltrate sensitive information from the server it could lead to the loss of customers, and the damaging of the companies reputation. A hacker or hacktivist group could do even more harm by installing malware, or locking down the system. Unethical customers could potentially alter or delete their information disrupting business. 

## Remediation Strategy

Implementation of authentication, authorization, and auditing mechanisms to ensure that only authorized users access the database server. This includes using strong passwords, role-based access controls, and multi-factor authentication to limit user privileges. Encryption of data in motion using TLS instead of SSL. IP allow-listing to corporate offices to prevent random users from the internet from connecting to the database.
