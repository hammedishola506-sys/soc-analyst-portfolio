# SIEM Alert Analysis – TryHackMe

## Alert 1: Phishing Email

Who: External sender posing as Microsoft Support targeting internal user  
What: Email flagged as phishing with suspicious attachment (REPORT.rar)  
When: March 27th 2025 at 19:25  
Where: Corporate email system  
Why: SPF and DKIM checks failed, suspicious urgency language used  

Conclusion: True Positive – Phishing attempt detected and escalated.


## Alert 2: Spike in Domain Discovery Commands

Who: Internal host/user account  
What: Spike in domain discovery commands indicating enumeration  
When: March 27th 2025 at 19:56  
Where: Internal network environment  
Why: Activity suggests reconnaissance behaviour  

Conclusion: True Positive – Escalated for further investigation.