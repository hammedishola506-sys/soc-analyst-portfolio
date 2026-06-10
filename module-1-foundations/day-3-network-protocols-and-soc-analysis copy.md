# Day 3: Network Security Protocols & Traffic Forensics

## Technical Overview
This module transitions foundational protocol knowledge directly into defensive SOC analysis. By breaking down deep packet layers (Layers 3, 4, and 7), this documentation demonstrates how a security analyst fingerprints specific applications and recognizes structural network anomalies.

---

## 🔬 Deep Packet Analysis Protocol Breakdown

### 1. Address Resolution Protocol (ARP) — Layer 2/3 Boundary
* **Function:** Dynamically maps a known Layer 3 IP address to a hardware Layer 2 MAC address.
* **Security Threat Matrix:** **ARP Spoofing / Poisoning**. Attackers send unsolicited ARP replies to link their MAC address with the default gateway IP, establishing a Man-in-the-Middle (MitM) positioning.
* **Analyst Detection:** Looking for rapid, duplicate MAC address claims for a single IP within toolsets or log sources.

### 2. Hypertext Transfer Protocol Secure (HTTPS) — Layer 7
* **Function:** Combines standard HTTP communication with TLS cryptographic encapsulation over port 443.
* **Security Threat Matrix:** Command and Control (C2) channels frequently hide beacons inside encrypted HTTPS payloads to bypass legacy firewall signature matching.
* **Analyst Detection:** Analyzing protocol negotiation attributes, anomalous JA3 TLS fingerprints, or identifying unexpected beaconing frequencies via Network Security Monitoring (NSM) sensors.

---

## 🛠️ SOC Engineering Implementation (Zeek & Suricata)
To transition from passive protocol observation to active enterprise defense, this lab infrastructure leverages a dedicated monitoring interface. 

### Core Inspection Engine Layer
* **Suricata Engine:** A high-performance Network IDS/IPS engine capable of matching signature patterns across live packet streams to alert on known exploit variants.
* **Zeek Engine (Bro):** A behavior-based network security monitoring tool that translates raw network packets into highly structured, searchable contextual log files (such as `conn.log`, `dns.log`, and `http.log`).

*(Analyst Note: Live configuration maps, signature file structures, and log parser examples will be appended as package deployment concludes.)*