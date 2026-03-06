# Module 1 – Networking Foundations
## Day 2 – IP Addressing and Subnetting

This document summarizes the networking concepts learned about IP addressing and subnetting and how they relate to security analysis.

---

## 1. Public vs Private IP Addresses

IP addresses uniquely identify devices on a network.

### Private IP Ranges (RFC 1918)

Private IP addresses are used inside internal networks and are not routable on the public internet.

10.0.0.0 – 10.255.255.255 (/8)

172.16.0.0 – 172.31.255.255 (/12)

192.168.0.0 – 192.168.255.255 (/16)

Example private address:

192.168.1.10

### Public IP Address

Public IP addresses are globally routable on the internet.

Example:

8.8.8.8

---

## 2. Special IPv4 Addresses

### Loopback Address

127.0.0.1

Used for a computer to communicate with itself (localhost).

---

### APIPA (Automatic Private IP Addressing)

Range:

169.254.0.0 – 169.254.255.255

This occurs when a device cannot reach a DHCP server and automatically assigns itself an address.

---

### Multicast Addresses

Range:

224.0.0.0 – 239.255.255.255

Used for one-to-many communication.

Example:

224.0.0.1

---

### Broadcast Address

Example:

255.255.255.255

Used to send traffic to all devices on a network.

Example DHCP process:

Source: 0.0.0.0  
Destination: 255.255.255.255

---

## 3. CIDR and Prefix Length

CIDR (Classless Inter-Domain Routing) defines how many bits belong to the network.

Example:

192.168.1.0/24

Meaning:

Network bits: 24  
Host bits: 8

---

## 4. Subnetting Fundamentals

Subnetting divides a large network into smaller logical networks.

Benefits include:

- Improved network segmentation
- Better security control
- Reduced broadcast traffic
- Easier troubleshooting

---

## 5. Host Calculation

Formula:

Host bits = 32 − prefix

Total addresses = 2^(host bits)

Usable hosts = 2^(host bits) − 2

Example:

/26 network

Host bits = 6  
Total addresses = 64  
Usable hosts = 62

---

## 6. Example Subnet

Network:

192.168.10.0/26

Range:

Network: 192.168.10.0  
First Host: 192.168.10.1  
Last Host: 192.168.10.62  
Broadcast: 192.168.10.63

---

## SOC Analyst Perspective

Understanding IP addressing helps security analysts:

- Identify internal vs external traffic
- Detect suspicious network activity
- Understand network segmentation
- Investigate lateral movement
- Analyze firewall and SIEM logs

Example investigation:

192.168.10.45 → suspicious external server

Subnet knowledge helps determine the affected network segment.

---

## Summary

Today we learned:

- Public vs Private IP addresses
- Special IPv4 addresses (Loopback, APIPA, Multicast, Broadcast)
- CIDR notation and prefix length
- Subnet masks and host calculations
- Why subnetting is important for security investigations