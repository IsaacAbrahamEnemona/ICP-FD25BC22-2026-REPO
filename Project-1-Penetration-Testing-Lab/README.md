Penetration Testing Lab

Overview
This project demonstrates a controlled penetration testing and vulnerability assessment exercise using **Kali Linux** and the intentionally vulnerable Metasploitable 2 virtual machine.
The objective was to perform reconnaissance, identify exposed and vulnerable services, validate a selected vulnerability through controlled exploitation, establish a post-exploitation session, verify the privileges obtained, document the evidence, and provide security recommendations based on the findings.
Environment: This assessment was conducted exclusively within an isolated laboratory environment using an intentionally vulnerable target.

Lab Environment

 Component               | Configuration     
 ----------------------- | ----------------- 
 Attacker Machine        | Kali Linux        
 Target Machine          | Metasploitable 2  
 Virtualization Platform | Oracle VirtualBox 
 Network Type            | Host-Only Network 
 Attacker IP             | 192.168.56.101  
 Target IP               | 192.168.56.102  

Objectives
1. Perform reconnaissance and network discovery.
2. Identify open ports and running services.
3. Enumerate potentially vulnerable services.
4. Validate selected vulnerabilities in the controlled laboratory environment.
5. Perform controlled exploitation of a confirmed vulnerability.
6. Establish and verify a post-exploitation session.
7. Document screenshots, video evidence, and technical findings.
8. Provide appropriate security recommendations.
9. Produce a professional penetration testing report.

Methodology
The assessment followed a structured penetration testing workflow:

Reconnaissance
      ↓
Service Enumeration
      ↓
Vulnerability Identification
      ↓
Controlled Exploitation
      ↓
Post-Exploitation
      ↓
Privilege Verification
      ↓
Documentation & Reporting

Key Finding
During service enumeration, the target was found to be running:

vsftpd 2.3.4 on FTP port 21
This version contains a known backdoor vulnerability that was validated in the controlled laboratory environment using the Metasploit Framework.
The exploitation successfully resulted in a Meterpreter session, after which root-level access was verified on the target.

Result
Compromise achieved: Yes
Post-exploitation session: Meterpreter
Privilege level verified: root (`uid=0`)

Tools Used
Kali Linux — Penetration testing operating system
Nmap — Network discovery and service enumeration
Metasploit Framework — Vulnerability validation and exploitation
Meterpreter — Post-exploitation session
Enum4linux — SMB/Samba enumeration
Netcat — Network testing
Oracle VirtualBox — Virtual laboratory environment

Evidence
Screenshots
The project contains five pieces of screenshot evidence documenting the assessment:
1. Network Configuration — Attacker and target network configuration.
2. Nmap Scan — Target discovery and exposed services.
3. VSFTPD Exploitation — Controlled exploitation of vsftpd 2.3.4.
4. Meterpreter Session — Successful post-exploitation session.
5. Root Access — Verification of root-level privileges.
See the complete evidence in [evidence/screenshots/](evidence/screenshots/).

Video Demonstration
A video demonstration of the penetration testing workflow is available in [evidence/video/](evidence/video/).

Project Structure

Project-1-Penetration-Testing-Lab/

├── README.md
│
├── documentation/
│   ├── methodology.md
│   └── scope-and-objectives.md
│
├── scans/
│   └── nmap-initial-scan.txt
│
├── exploitation/
│   ├── vsftpd/
│   │   └── README.md
│   └── samba/
│       └── README.md
│
├── evidence/
│   ├── screenshots/
│   │   ├── README.md
│   │   ├── screenshot-1-network-configuration.png
│   │   ├── screenshot-2-nmap-scan.png
│   │   ├── screenshot-3-vsftpd-exploitation.png
│   │   ├── screenshot-4-meterpreter-session.png
│   │   └── screenshot-5-root-access.png
│   │
│   └── video/
│       ├── README.md
│       └── penetration-testing-Lab.mp4
│
└── report/
    └── penetration-testing-report.md

Findings & Recommendations

Critical — vsftpd 2.3.4 Backdoor

Affected Service: FTP
Port: 21/tcp
Target: 192.168.56.102
Impact: Successful exploitation provided unauthorized access to the target and allowed root-level privileges to be verified.

Recommendations:
Upgrade or remove the vulnerable vsftpd version.
Apply security patches regularly.
Disable unnecessary network services.
Restrict access to administrative services using firewall rules.
Monitor exposed services for suspicious activity.
Use secure alternatives such as SFTP where appropriate.
Conduct regular vulnerability assessments.

Assessment Outcome
The assessment successfully demonstrated the complete penetration testing lifecycle against the intentionally vulnerable target:
Reconnaissance → Enumeration → Vulnerability Identification → Exploitation → Meterpreter → Root Verification
The exercise demonstrates the security impact of running outdated and vulnerable services and highlights the importance of patch management, service hardening, network segmentation, and continuous security monitoring.

Disclaimer
This project was performed exclusively in an isolated, intentionally vulnerable laboratory environment for educational and authorized cybersecurity training purposes.

The techniques demonstrated in this project should only be used against systems for which explicit authorization has beerovided.
