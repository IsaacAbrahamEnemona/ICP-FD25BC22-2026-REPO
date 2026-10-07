Penetration Testing Report

Metasploitable Vulnerability Assessment & Exploitation Lab

Project: Penetration Testing Lab
Assessment Type: Vulnerability Assessment & Penetration Testing
Attacker Machine: Kali Linux
Target Machine: Metasploitable 2
Target IP: 192.168.56.102
Attacker IP: 192.168.56.101
Network: VirtualBox Host-Only Network

 1. Executive Summary
This penetration testing assessment was conducted against an intentionally vulnerable Metasploitable 2 virtual machine in an isolated laboratory environment.
The objective was to identify exposed services, assess potential vulnerabilities, demonstrate controlled exploitation of a confirmed vulnerability, establish a Meterpreter session, and verify the level of access obtained.
During reconnaissance, multiple network services were identified on the target system. The FTP service running vsftpd 2.3.4 was identified as a critical security weakness.
The vulnerable FTP service was successfully exploited using the Metasploit Framework. A Meterpreter session was established and root-level privileges were subsequently verified on the target system.
The assessment demonstrates how an exposed vulnerable service can provide an attacker with unauthorized privileged access when appropriate security controls and patching are absent.
2. Scope and Objectives
2.1 Scope
The assessment was limited to the intentionally vulnerable Metasploitable 2 virtual machine:
Target: 192.168.56.102
Testing was performed from the Kali Linux attacker machine:

Attacker: 192.168.56.101

2.2 Objectives
The objectives of the assessment were to:
 Identify the target system and exposed services.
 Perform network and service reconnaissance.
 Identify potentially vulnerable services.
 Validate a confirmed vulnerability through controlled exploitation.
 Establish a post-exploitation session.
 Verify the privileges obtained.
 Document findings and recommend appropriate remediation.

 3. Methodology
The assessment followed a simplified penetration-testing methodology:

Reconnaissance
      ↓
Service Enumeration
      ↓
Vulnerability Identification
      ↓
Exploitation
      ↓
Post-Exploitation
      ↓
Privilege Verification
      ↓
Documentation & Remediation

3.1 Reconnaissance
The target network configuration was verified to ensure communication between Kali Linux and Metasploitable.
The lab used a VirtualBox Host-Only network.
 Kali Linux: 192.168.56.101
Metasploitable: 192.168.56.102

3.2 Service Enumeration
Nmap was used to identify open ports and running services on the target.
The scan identified several exposed services, including:

 FTP
 SSH
 Telnet
 SMTP
 DNS
 HTTP
 RPC
 SMB/Samba
The FTP service was particularly significant because the target was running vsftpd 2.3.4, a version associated with a known backdoor vulnerability.

3.3 Vulnerability Identification
The vsftpd service was identified on:
Port: 21/tcp
Service: FTP
Version: vsftpd 2.3.4
The service was selected for controlled exploitation because the laboratory target intentionally contains this known vulnerable version.

 3.4 Exploitation
The Metasploit Framework was used to validate the vulnerability.

The exploit module used was:
exploit/unix/ftp/vsftpd_234_backdoor

The target was configured as:
RHOSTS = 192.168.56.102
The Kali Linux host was configured as:
LHOST = 192.168.56.101
The exploit was then executed against the laboratory target.

3.5 Post-Exploitation
Following successful exploitation, a Meterpreter session was established with the target system.
The session was verified using Meterpreter commands such as:
getuid
sysinfo
The session confirmed access to the compromised system.

3.6 Privilege Verification
A shell was opened from the Meterpreter session and the user's privileges were verified.
Commands used included:
shell
whoami
id
The resulting output confirmed:
uid=0(root)

This demonstrated that the compromised target had been accessed with root-level privileges.

4. Findings
 Finding 01 — vsftpd 2.3.4 Backdoor
Severity: Critical
Affected Service: FTP
Port: 21/tcp
Affected Host: 192.168.56.102

Description:
The target system was running vsftpd 2.3.4, a vulnerable version of the FTP server associated with a malicious backdoor.
The vulnerability allowed the service to be exploited remotely in the laboratory environment.

Impact:
Successful exploitation resulted in unauthorized access to the target system and ultimately provided root-level privileges.
An attacker exploiting a similarly exposed vulnerable service could potentially:

Execute commands on the affected system.
Access sensitive files.
Modify system configurations.
Install malicious software.
Establish persistence.
Use the compromised host as a foothold for further attacks.

Recommendation:
Remove or upgrade the vulnerable version of vsftpd.
Apply current security patches.
Disable unnecessary FTP services.
Restrict FTP access using firewall rules.
Monitor exposed services for suspicious activity.
Use secure alternatives such as SFTP where appropriate.

5. Evidence
The assessment evidence is stored in the project's evidence directory.

Screenshots
 Evidence                                  | Description                                         
 ----------------------------------------- | --------------------------------------------------- 
 screenshot-1-network-configuration.png | Network configuration of the laboratory environment 
 screenshot-2-nmap-scan.png             | Nmap reconnaissance and service enumeration         
 screenshot-3-vsftpd-exploitation.png   | Controlled exploitation of vsftpd 2.3.4             
 screenshot-4-meterpreter-session.png   | Successful Meterpreter session                      
 screenshot-5-root-access.png           | Verification of root-level privileges               

Video Evidence
The video evidence demonstrates the penetration-testing workflow from reconnaissance through exploitation and privilege verification.

6. Risk Assessment
 Finding               | Severity | Likelihood | Impact   
  -------------------- | -------- | ---------- | -------- 
 vsftpd 2.3.4 Backdoor | Critical | High       | Critical |

The combination of a remotely accessible vulnerable service and successful exploitation represents a critical security risk.

7. Remediation Summary
The following actions are recommended:
1. Upgrade or remove vsftpd 2.3.4.
2. Apply security patches regularly.
3. Disable services that are not required.
4. Restrict network access to administrative services.
5. Implement host-based and network firewalls.
6. Monitor authentication and network activity.
7. Conduct regular vulnerability assessments.
8. Maintain an accurate inventory of exposed services.

8. Conclusion
The penetration testing assessment successfully demonstrated the security risks associated with running outdated and vulnerable network services.
The assessment identified the vulnerable vsftpd 2.3.4 FTP service and successfully validated the associated vulnerability using the Metasploit Framework.
The exploitation resulted in a Meterpreter session and root-level access to the intentionally vulnerable target.
This laboratory exercise demonstrates the importance of vulnerability management, service hardening, security patching, network segmentation, and continuous security monitoring.
The findings and evidence documented in this report provide a complete record of the assessment performed against the laboratory target.

9. Tools Used
 Kali Linux
 Nmap
 Metasploit Framework
 Meterpreter
 VirtualBox
 Metasploitable 2

10. Ethical and Legal Notice
This assessment was performed exclusively against an intentionally vulnerable virtual machine in an isolated laboratory environment.
The techniques documented in this project are intended for authorized security testing, cybersecurity education, vulnerability assessment, and penetration-testing practice.
Unauthorized testing against systems without explicit permission is prohibited.
