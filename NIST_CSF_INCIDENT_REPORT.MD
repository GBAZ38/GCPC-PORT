# ACTIVITY OVERVIEW

In this activity, you will create an incident report using the knowledge you’ve gained about networks throughout this course to analyze a network incident. You will analyze the situation using the National Institute of Standards and Technology's Cybersecurity Framework (NIST CSF). The CSF is a voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk. Creating a quality cybersecurity incident report and applying the CSF can demonstrate a proactive approach to security, improving communication and transparency with stakeholders, and improve security practices within your organization. You can also add the incident report you create to your cybersecurity portfolio when  you complete it.

The CSF is scalable and can be applied in a wide variety of contexts. As you continue to learn more and refine your understanding of key cybersecurity skills, you can use the templates provided in this activity in other situations. Knowing how to identify which security measures to apply in response to business needs will help you determine which are the best available options when it comes to network security.

---------

## SCENARIO

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack. 

To address this security event, the network security team implemented: 
1. A new firewall rule to limit the rate of incoming ICMP packets
2. Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets
3. Network monitoring software to detect abnormal traffic patterns
4. An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

1. Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security. 
2. Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats. 
3. Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections. 
4. Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process. 
5. Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident. 
------------
### ACTIVITY

SUMMARY: While working as a cybersecurity analyst at a multimedia company that offers different marketing solutions to small businesses, we expericed a distributed denial of service (DDoS) attack that compromised the internal network for two hours. During the attack network services suddenly stopped responding due to an incoming flood of internet communication management protocol (ICMP) packets. Due to the ICMP spam normal traffic could not access any network resources. After reviewing the network traffic, and realizing what was happening, the incident management team blocked all ICMP packets. In doing so they stopped all non-critical network services affline, and restored critical network services. After the cybersecurity team investigated the event. They found that a malicious actor had sent a flood of ICMP pings into the company's network through an unconfigured firewall. This vulnerability allowed the malicious actor to overwhelm the company's network through a distributed denial of service (DDoS) attack. In this event a malicious actor targeted the company's network and flooded their servers with ICMP packets. The perpetrator of the attack is someone who had access to multiple devices and used them to orchistrate a distributed denial of service attack. The attack affected not only the company and its employees, but also the customers who relied on the company's internal network, for two hours.

IDENTIFY: In this event the company was the victim of a distributed denial of service (DDoS) attack. A DDoS is a type of network disruption that occurs when multiple devices are used to overwhelm a target system, such as a server or network by sending many information requests repeatedly in a short amount of time. Because of the flood of network traffic the network is unable to be accessed by customers and employees that rely on its infrustructure, and therefore we have a distributed denial of service (DDoS) attack.

PROTECT:  
