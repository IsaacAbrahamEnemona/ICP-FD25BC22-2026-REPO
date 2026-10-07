Screenshot Evidence

This directory contains screenshots captured during the penetration testing lab against the intentionally vulnerable Metasploitable virtual machine.

Evidence 1 — Network Configuration
File: `screenshot-1-network-configuration.png`

Shows the network configuration used to establish communication between the Kali Linux attacker machine and the Metasploitable target.
Kali Linux: 192/168.56.101
Metasploitable: 192.168.56.102
Network: VirtualBox Host-Only Network

Evidence 2 — Nmap Scan
File: screenshot-2-nmap-scan.pn`

Shows the reconnaissance and service enumeration performed against the Metasploitable target. The scan identified exposed services, including FTP and other network services.
Target: 192.168.56.102

Evidence 3 — VSFTPD Exploitation
File: screenshot-3-vsftpd-exploitation.png
Shows the exploitation of the vulnerable vsftpd 2.3.4 FTP service using Metasploit.
Target: 192.168.56.102
Service: FTP — Port 21
Vulnerability: vsftpd 2.3.4 backdoor

Evidence 4 — Meterpreter Session
File: screenshot-4-meterpreter-session.png
Shows the successful establishment and interaction with a Meterpreter session on the vulnerable target.

Evidence 5 — Root Access
File: screenshot-5-root-access.png
Shows verification of elevated privileges on the compromised Metasploitable system.

The session confirmed root-level access (`uid=0`) on the intentionally vulnerable target.

Evidence Summary
    | Evidence              | Purpose                                                
 -- | --------------------- | ------------------------------------------------------ 
 01 | Network Configuration | Verify attacker and target connectivity                
 02 | Nmap Scan             | Identify exposed services                              
 03 | VSFTPD Exploitation   | Demonstrate exploitation of the vulnerable FTP service 
 04 | Meterpreter Session   | Demonstrate successful session establishment           
 05 | Root Access           | Verify elevated privileges                             
> **Lab Note:** This penetration test was performed in an isolated virtual lab using intentionally vulnerable systems for educational and authorized security testing purposes.
