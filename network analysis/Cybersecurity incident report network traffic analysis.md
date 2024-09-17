# Cybersecurity Incident Report: 

## Network Traffic Analysis

| Part 1: Provide a summary of the problem found in the DNS and ICMP  traffic log.  |
| :---- |
| The UDP protocol reveals that: our computer attempts to use the UDP protocol to request the ip address of yummyrecipesforme.com from the DNS server using a UDP packet\.
This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message: ICMP 203.0.113.2 UDP port 53 unreachable length 254\.
The port noted in the error message is: port 53 is a port used for DNS service\.
The most likely issue is: the word “unreachable” indicates the UDP message requesting an IP address for the domain “[www.yummyrecipesforme.com](http://www.yummyrecipesforme.com)” did not go through to the DNS server because no service was listening on the receiving DNS port, port 53\.  |

| Part 2: Explain your analysis of the data and provide at least one cause of the incident. |
| :---- |
| Time incident occurred: approx 13:24:32.192571\.

Explain how the IT team became aware of the incident: Several customers of clients reported that they were not able to access the client company website [www.yummyrecipesforme.com](http://www.yummyrecipesforme.com/), and saw the error “destination port unreachable” after waiting for the page to load\.

Explain the actions taken by the IT department to investigate the incident: To start, we attempt to visit the website and we also receive the error “destination port unreachable.” To troubleshoot the issue, we load our network analyzer tool, tcpdump, and attempt to load the webpage again, while also documenting the tcpdump output\.

Note key findings of the IT department's investigation (i.e., details related to the port affected, DNS server, etc.): ICMP echo reply returned the error message: ICMP 203.0.113.2 UDP port 53 unreachable length 254\. Port 53 is a port used for DNS service\. No service was listening on the receiving DNS port\.

Note a likely cause of the incident: no service was listening on the receiving DNS port\. |
