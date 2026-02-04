# Network Traffic Analysis - Cybersecurity Incident Report

## Project Overview
This project consists of an analysis of a network security incident involving **DNS** and **ICMP** protocols. The objective was to investigate why users were unable to access a specific web domain and determine the root cause using network packet analysis.

## Scenario
* **Domain:** `www.yummyrecipesforme.com`
* **Symptoms:** Customers reported "destination port unreachable" errors when trying to load the website.
* **Tools Used:** `tcpdump` for packet capture and log analysis.

* ![Análisis de Tráfico DNS](referencia%201.png)

## Key Findings & Analysis
Based on the `tcpdump` log analysis, the following technical details were identified:

* **Failed DNS Resolution:** The UDP traffic shows that the client (IP 192.51.100.15) attempted to resolve the domain at the DNS server (IP 203.0.113.2).
* **ICMP Error Messages:** The server returned "UDP port 53 unreachable" messages, indicating the request reached the destination but the port was closed.
* **Protocol Impact:** The **UDP** protocol (used for DNS queries on port 53) was unable to complete the request.
* **Timeline:** Three specific connection attempts were logged at 1:24 PM, 1:26 PM, and 1:28 PM.



## Root Cause Determination
The most likely cause of the incident is that the **DNS service** on the destination server is inactive or the traffic is being blocked by a **Firewall** configuration.

## Recommended Next Steps
1.  **Service Verification:** Verify the status of the DNS service on the target server.
2.  **Firewall Audit:** Audit recent Firewall rule changes to ensure Port 53 is open for incoming UDP traffic.
3.  **External Investigation:** Coordinate with the DNS provider to check logs for signs of a malicious incident or service outage.

## Skills Demonstrated
* Network Protocol Analysis (TCP/IP, DNS, ICMP, UDP).
* Traffic Log Interpretation using `tcpdump`.
* Incident Reporting and Documentation.
* Cybersecurity Troubleshooting.
