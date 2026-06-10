# Day 2: Core Networking Fundamentals — IP Addressing & Subnetting

## Technical Overview
A Security Operations Center (SOC) Analyst must possess a granular understanding of IP addressing, subnet masking, and CIDR notation. Network segmentation is one of the primary defensive barriers an enterprise uses to restrict lateral movement during an active breach. This module covers core network boundary logic and traffic segregation tracking.

---

## 🧭 Subnet Architecture & Boundary Analysis

### 1. IPv4 Architecture Fundamentals
* **Structure:** 32-bit logical address broken down into four 8-bit octets separated by dots.
* **Component Split:** Every IP address is divided into a **Network ID** (routing path) and a **Host ID** (specific endpoint device).

### 2. Classless Inter-Domain Routing (CIDR)
* **Mechanics:** CIDR notation specifies exactly how many bits of an IP address belong to the network identifier.
* **Example Analysis (`/24`):** A subnet mask of `255.255.255.0` reserves 24 bits for the network, leaving 8 bits for hosts ($2^8 - 2 = 254$ usable host addresses). 

### 3. Enterprise Traffic Segmentation
* **Private vs. Public Boundaries:** Documentation of RFC 1918 address space used inside the internal architecture to prevent direct exposure to the public internet:
  * `10.0.0.0/8`
  * `172.16.0.0/12`
  * `192.168.0.0/16`

---

## 🛡️ Security Implications & Defensive Blueprinting
* **Lateral Movement Containment:** Proper subnet masking prevents a compromised machine in a public-facing DMZ from freely accessing sensitive domain controllers or database clusters in internal zones.
* **Asset Tracking:** Assigning deterministic subnets allows a SOC Analyst to rapidly identify device context (e.g., recognizing that an alert originating from a `10.100.4.0/24` range means a finance department desktop is initiating an external port scan).

---

## 🛠️ Validation Metrics
* **Lab Reference Network:** `192.168.193.0/24`
* **Sensor Node Target:** `192.168.193.131` (Ubuntu Linux running Network Security Monitoring stack)