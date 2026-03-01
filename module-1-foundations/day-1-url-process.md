## Key Security Risks Identified



# Day 1 – What Happens When You Type a URL in a Browser

This document explains the full technical process from DNS resolution to TCP handshake, TLS negotiation, and secure HTTP communication, including associated security risks and defensive controls.

---

- DNS Spoofing / DNS Cache Poisoning  
- SYN Flood (DoS / DDoS)  
- On-path (MITM) attack during TLS negotiation  
- Certificate validation failure risks  

## Defensive Controls

- DNSSEC  
- HTTPS (TLS encryption)  
- SYN cookies  
- Certificate Authority trust chain validation  

