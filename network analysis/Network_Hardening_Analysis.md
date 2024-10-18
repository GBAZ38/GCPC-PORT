
# Network Hardening Analysis

## Activity Overview

In this activity, you will be presented with a scenario about a social media organization that recently experienced a major data breach caused by undetected vulnerabilities. To address the breach, you will identify some common network hardening tools that can be implemented to protect the organization’s overall security. Then, you will select a specific vulnerability that the company has and propose different network hardening methods. Finally, you will explain how the methods and tools you chose will be effective for managing the vulnerability and how they will prevent potential breaches in the future.<br>

In the course, you learned network hardening and network security-related hardening practices, such as port filtering, network access privileges, and encryption over networks. Network hardening practices help organizations monitor potential threats and attacks on their network and prevent some attacks from occurring. Some hardening practices are implemented every day, while others are executed every once in a while, such as every other week or once a month. Understanding how to use network hardening tools and methods will help you better monitor network activity and protect your organization’s network against various attacks.<br>


## Scenario

You are a security analyst working for a social media organization. The organization recently experienced a major data breach, which compromised the safety of their customers’ personal information, such as names and addresses. Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future.<br>

After inspecting the organization’s network, you discover four major vulnerabilities. The four vulnerabilities are as follows:
1. The organization’s employees' share passwords.
2. The admin password for the database is set to the default.
3. The firewalls do not have rules in place to filter traffic coming in and out of the network.
4. Multifactor authentication (MFA) is not used. 

If no action is taken to address these vulnerabilities, the organization is at risk of experiencing another data breach or other attacks in the future.<br>

In this activity, you will write a security risk assessment to analyze the incident and explain what methods can be used to further secure the network.<br>

## Security risk assessment report:

Select up to three hardening tools and methods to implement:
1. Set up password policies requiring unique employee ids and passwords
2. Implement port filtering
3. Enable MFA

Explain your recommendations:

The use of weak or repeat passwords allow a malicous actor to gain access to a mass number of accounts. The National Institute of Standards and Technologys (NIST) latest recommendation for password policies focuses on using methods to salt and hash passwords. Salting is the addition of a random unique value to a password before hashing. This prevents rainbow table attacks by making it impossible to precompute hashes for common passwords. Salting also ensures that even if two users use the same password their hashes will be different. Hashes are the result of a one way mathematical function that transforms the password into a fixed-size string of characters. Hashing by design is computationally expensive and slow in order to make brute-force attacks more difficult. By utilizing salt and hash you can create a robust password storage mechanism that could protect both employee, and user credentials from unauthorized access.

Port filtering is used to control network traffic and can prevent potenial attackers from entering a private network. By blocking traffic from unwanted or unused network ports system administrators reduce the risk of dangerous traffic, or network exploits. This is typically done by using a software or hardware firewall that can be configured to meet a companies needs.

Multifactor authentication (MFA) is a security measure that requires a user to verify their identity in two or more ways when accessing a system or network. MFA options often include passwords, pin numbers, biometrics (such as finger print or face ID), RFID badge, and one-time password (OTP) to name a few. Enabling MFA helps reduce the risk of brute-force attacks and similar security events.
