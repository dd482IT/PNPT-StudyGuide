Pentration Test Phases

Penetration Test Goal: Gain SYSTEM-level access within a domain environment is nearly equivalent to having a domain user account. 

1. Reconnaissance	
What information can be collected about the target. What possible pathways and attack vectors are present. What vulnerabilities might be present? What users are present? Use this area to develop your approach for the next phase.
- Goals: Identify the domain controller. 
3. Initial Access
Given you collected some information about your target and you see an attack vector that can be exploited either through a phish, a Web App Vulnerability or perhaps through a misconfiguration. Determine what tools are needed. 
4. Execution	
   If you attempt at inital access is a complex, you may need to have more information here as to how the exploit will be executed. 
5. Persistence	
Once you have access, access being a shell or some sort of way to interact with the system, how will you ensure this can be maintained? Setup persistance with metasploit. 
6. Privilege Escalation / Enumeration
- Now that you have persistence, you can return to the system to continue the assessment. Keep in mind, the system you are exploiting may not be vulnerable to privilege escalation so focus on understanding what the system is, it's function and interconnectivity with other (potentially vulnerable systems).
- Identifying Potential Vulnerabilities can allow you gain high privs.

6. Defense Evasion
   - PNPT may or may not have defenses in place
8. Credential Access Discovery	
This falls under intial access or privilege escalation. 
9. Lateral Movement

