# cybersecurityinternship-task-1: Local Network Port Scan 
## Objective  
 Learn to discover open ports on devices in your local network to understand network exposure.
 Tools Used: 
    -Nmap(free) – TCP SYN scanning  
    -Windows 11 + Command Prompt 
## Execution Steps

 1 Install Nmap-Downloaded & installed from [nmap.org/download](https://nmap.org/download) with Npcap
 2 Find local IP range- Ran ipconfig → Identified network: 10.0.0.0/24 
 3 Run TCP SYN scan-cmd\nmap -sS 10.0.0.0/24 -oN scan.txt 
 4 Note IP addresses & open ports-2 hosts up → 10.0.0.1 & 10.0.0.100 
 5 Research services like DNS, RPC, SMB, UPnP, WSD |
 7 Identify risks
 8 Save results scan.txt 

## Key Findings

 Open Ports     Service                    Common Use                              Security Risk
 53/tcp          DNS                      Domain resolution                 Zone transfer, DNS spoofing, amplification DDoS 
 135/tcp         MSRPC                    Remote Procedure Call             Remote code execution (e.g., MS08-067) 
 139/tcp         NetBIOS-SSN              File/printer sharing              Credential theft, lateral movement 
 445/tcp         Microsoft-DS (SMB)        File sharing                      WannaCry, EternalBlue, PrintNightmare
 2869/tcp       ICSLAP (UPnP)             Device discovery                  SSDP reflection DDoS attacks
 5357/tcp        WSDAPI                   Web Services on Devices           Printer/service enumeration
 -2 hosts up
 -6 open ports: 53 (DNS), 135/139/445 (SMB/RPC), 2869 (UPnP), 5357 (WSD)
 -High risk: SMB (445)

-Critical Note: SMB (445) + RPC (135) = High-risk combo on Windows → Common in ransomware attacks.


## Final Notes

Outcome Achieved:  
  - Mastered network reconnaissance 
  - Understood service exposure risks  
  - Applied real-world security thinking  



