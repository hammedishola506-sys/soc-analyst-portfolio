# Day 1: What Happens When You Type a URL in a Browser?

## Technical Process Overview
This document explains the full end-to-end technical process that occurs when a user requests a website, tracking data from DNS resolution through the TCP handshake, TLS negotiation, and secure HTTP communication. Understanding this baseline traffic is critical for distinguishing normal user behavior from malicious network activity.

---

## 🔍 Detailed Network Flow

### 1. DNS Resolution
* **Process:** The browser checks local cache, then queries the OS DNS resolver to translate the human-readable domain name into an architecture-routable IPv4 address.
* **Security Risk:** **DNS Spoofing / DNS Cache Poisoning**. Attackers can alter DNS records to redirect traffic to a malicious lookalike site.
* **Defensive Control:** Implement **DNSSEC** (Domain Name System Security Extensions) to cryptographically sign DNS records and ensure data integrity.

### 2. TCP Handshake (Layer 4)
* **Process:** A reliable connection is established using the standard 3-way handshake:
  1. `SYN` (Client to Server)
  2. `SYN-ACK` (Server to Client)
  3. `ACK` (Client to Server)
* **Security Risk:** **SYN Flood (DoS / DDoS)**. Attackers send a massive volume of `SYN` requests but never respond to the `SYN-ACK`, exhausting server resources.
* **Defensive Control:** Enable **SYN Cookies** on the host operating system to handle half-open connections without consuming system memory.

### 3. TLS Negotiation (Cryptographic Layer)
* **Process:** The client and server agree on cipher suites, authenticate the server's identity using digital certificates, and generate symmetric session keys for data encryption.
* **Security Risk:** **On-Path (MitM) Attacks**. Attackers attempt to intercept the handshake or present fraudulent certificates.
* **Defensive Control:** Enforce strict **Certificate Validation** and deployment of **HSTS** (HTTP Strict Transport Security) to protect against protocol downgrade attacks.

---

## 🛠️ SOC Analyst Verification Lab
* **Objective:** Capture and analyze standard browser traffic using network monitoring utilities.
* **Tooling Used:** Wireshark Packet Analyzer 

*(Analyst Note: Insert your Wireshark packet capture screenshot showing the DNS query or the TCP 3-way handshake here to demonstrate validation validation capabilities.)*

