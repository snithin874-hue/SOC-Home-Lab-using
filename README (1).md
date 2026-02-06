# SOC-HOME-SETUP
Indroduction: 

This project establishes a Security Operations Center (SOC) home lab environment to emulate real-world cyberattacks and detection capabilities using Splunk, incorporating log forwarding, attack simulation, and alert generation to demonstrate comprehensive security monitoring and incident detection.  

Lab Overview :

Attacker: A Kali Linux system, serving as the dedicated platform for executing security assessments and simulated attacks.   

Victim : An Ubuntu server configured with multiple services, including a deliberately vulnerable web application, SSH, and FTP, to act as the target for the offensive host.

Monitoring Tool: A Windows server running Splunk Enterprise professional, which functions as the central SIEM for log aggregation, analysis, and alerting.  

Technologies Used :

SIEM Platform: Splunk Enterprise, deployed on a Windows server.

Log Agent: Splunk Universal Forwarder, installed on the Ubuntu target machine to forward logs.

Attack Simulation: A Kali Linux machine for conducting offensive security operations.

Virtualization Environment: VirtualBox or an equivalent hypervisor to host the virtual machines.

Target Services: Apache2 web server, vsftpd for FTP, and a custom login page on the Ubuntu target.    

Implementation Procedure: 

1.Configure Ubuntu (Target)-
.Install Apache, FTP, SSH and a custom vulnerable login page.
.Install and configure the Splunk Universal Forwarder.
.Forward /var/log/auth.log and /var/log/apache2/* to the Splunk server.

2.Configure Splunk Server (Windows)
.Install Splunk Enterprise.
.Configure inputs for receiving logs from the forwarder.
.Create dashboards and alerts.

3.Launch Attacks from Kali
.SSH brute-force using hydra.
.Web login brute-force using hydra or wfuzz.
.Web directory enumeration using gobuster.
.FTP anonymous login attempts.
.Trigger Windows failed logins manually for detection.     
       
 Detection Rules: 
 
.SSH Brute Force Detection

.Web Login Brute Force Detection

.Web Directory Enumeration

.FTP Anonymous Login Detection

.Windows Failed Login Attempts

Screenshot:


<img width="1919" height="939" alt="Screenshot 2026-02-03 170041" src="https://github.com/user-attachments/assets/5c3922f9-9de0-4d51-bda4-82b5f56bfb0d" />

<img width="1885" height="905" alt="Screenshot 2026-01-31 180555" src="https://github.com/user-attachments/assets/e23afa01-5638-402e-83aa-b3dcbb1a9ae9" />

<img width="1897" height="721" alt="Screenshot 2026-01-31 180118" src="https://github.com/user-attachments/assets/889a8afe-577c-4421-9027-ab66afb32c0f" />

<img width="1877" height="842" alt="Screenshot 2026-01-31 180714" src="https://github.com/user-attachments/assets/174ce7e6-875a-45d4-ad1a-b579aa1c91c8" />


Learning Outcomes:

Analyzed security logs to identify anomalies, threats, and attack patterns.

Developed incident investigation workflows using Splunk searches and correlation rules.

Improved understanding of SOC operations and real-world security monitoring processes.

Tuned detection rules to reduce false positives and improve alert accuracy.

Gained experience working with Linux and Windows log sources in an enterprise-style environment.


Future Improvements:

Implement an ELK Stack–based SIEM deployment for comparative analysis and expanded monitoring capabilities.

Integrate Suricata and Zeek to enable packet-level network detection and deeper traffic inspection.

Automate log parsing and normalization using custom field extractions, props, and transforms to improve detection accuracy and operational efficiency.

