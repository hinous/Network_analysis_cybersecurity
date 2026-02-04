# Network Traffic Analysis - Cybersecurity Incident Report

## Project Overview
This project consists of an analysis of a network security incident involving **DNS** and **ICMP** protocols. The objective was to investigate why users were unable to access a specific web domain and determine the root cause using network packet analysis.

## Scenario
* [cite_start]**Domain:** `www.yummyrecipesforme.com` [cite: 21]
* [cite_start]**Symptoms:** Customers reported "destination port unreachable" errors when trying to load the website. [cite: 9]
* [cite_start]**Tools Used:** `tcpdump` for packet capture and log analysis. [cite: 10, 22]

## Key Findings & Analysis
Based on the `tcpdump` log analysis, the following technical details were identified:

* [cite_start]**Failed DNS Resolution:** The UDP traffic shows that the client (IP `192.51.100.15`) attempted to resolve the domain at the DNS server (IP `203.0.113.2`). [cite: 15, 22]
* [cite_start]**ICMP Error Messages:** The server returned "UDP port 53 unreachable" messages. [cite: 15, 16]
* [cite_start]**Protocol Impact:** The **UDP** protocol (used for DNS queries on port 53) was unable to complete the request due to the port being closed or blocked. [cite: 15, 17]
* [cite_start]**Timeline:** Three specific connection attempts were logged at 1:24 PM, 1:26 PM, and 1:28 PM. [cite: 20]



## Root Cause Determination
[cite_start]The most likely cause of the incident is that the **DNS service** on the destination server is inactive or the traffic is being blocked by a **Firewall** configuration. [cite: 18, 24]

## Recommended Next Steps
1.  [cite_start]Verify the status of the DNS service on the target server. [cite: 26]
2.  [cite_start]Audit recent Firewall rule changes to ensure Port 53 is open for incoming UDP traffic. [cite: 26]
3.  [cite_start]Coordinate with the DNS provider to check logs for signs of a malicious incident (e.g., DoS attack). [cite: 26]

## Skills Demonstrated
* Network Protocol Analysis (TCP/IP, DNS, ICMP, UDP).
* Traffic Log Interpretation using `tcpdump`.
* Incident Reporting and Documentation.
* Cybersecurity Troubleshooting.
