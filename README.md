# Local-Network-Security-Assessment
Hands-on network discovery, port scanning, and packet analysis using Nmap and Wireshark.
# Local Network Security Assessment & Packet Analysis

## Project Description
This project demonstrates practical network engineering skills by executing active network discovery, service auditing, and real-time packet capturing on a local wireless subnet. The objective is to identify active hosts within a gateway range, map out open ports/exposed system services, and decode live network traffic streams.

## Infrastructure & Tools Used
* **Network Environment:** Live Local Wireless Hotspot Subnet (`192.168.61.0/24`)
* **Host Operating System:** Windows 11 Home
* **Discovery Tool:** Nmap CLI (v7.99)
* **Protocol Analyzer:** Wireshark

---

## Step-by-Step Implementation

### PHASE 1: Subnet Reconnaissance & Host Discovery
Determined the active network perimeter by running an ICMP ping sweep across the entire local `/24` subnet. This mapped out all live network devices communicating through the gateway.
```text
nmap -sn 192.168.61.0/24
Results: * Found 2 active hosts on the network.
​Identified Host 192.168.61.1 as the active network interface and 192.168.61.254 as the host machine's virtual network card

### PHASE 2: Port Scanning & Attack Surface Auditing
​Conducted a full TCP port scan against the target IP to audit running services and evaluate potential network vulnerabilities
nmap 192.168.61.1
Discovered Open Ports & Services:
​Port 135/tcp (msrpc): Microsoft Remote Procedure Call
​Port 139/tcp (netbios-ssn): NetBIOS Session Service
​Port 445/tcp (microsoft-ds): Microsoft Directory Services (SMB File Sharing

​### PHASE 3: Real-Time Traffic Analysis
​Utilized Wireshark to sniff and monitor live network communication frames over the active Wi-Fi interface.
​Layer 4 Analysis (UDP): Inspected service discovery multicast traffic targeting network address 239.255.255.250.
​Layer 4 Analysis (TCP): Captured dynamic HTTPS secure web traffic handshakes (Port 443) running via modern IPv6 transport configurations.

Core Engineering Takeaways:
​Hand-on experience calculating subnets and processing local network map ranges.
​Practical understanding of system vulnerabilities, noting that open SMB ports (445) represent critical vectors that require network Access Control Lists (ACLs) to secure.
​Proficiency in analyzing live packet capturing data to identify protocol traffic states.



