# T-Pot Honeypot Security Lab

## Overview
This project was designed to provide a isolated and secure virtual playground to learn reconnaissance tools, like Nmap on kali linux, and see how those tools are captured on a honeypot and can be analyzed.

The lab was built using VMware and consists of 3 VMs: 
Kali Linux
ubuntu server 24.04 hosting T-pot
ubuntu desktop

Kali Linux was used to generate a controlled network scan across the network, T-Pot server was used to pick up that traffic, The ubuntu desktop was used to display the traffic using Kibana on a monitoring platform.

The entire project was hosted on a personal server using Ubuntu 26.04 LTS on a dedicated virtual network to prevent simulated attacks from affecting the home network.
## Objectives
-build a isolated virtual network
-deploy and troubleshoot t-pot
-Use Nmap on kali linux to produce traffic across the network
-analyze the traffic using Kibana on the virtual desktop
-document the detection and analysis process
-deploy a secure remote access point to continue working on this during the UH semester using wireguard(in progress)
## Lab Architecture
```text
                    Host Server
                        |
                VMware Virtual Network
                        |
          +-------------+-------------+
          |             |             |
          v             v             v
      Kali Linux      T-Pot       Ubuntu Desktop
      (red-team)     Honeypot        Analysis
                   (blue-team)
```
## Technologies Used
Linux 
    Ubuntu desktop
    Ubuntu 26.04 server
    Kali linux
VMware
KVM
Nmap
Kibana
Suricata
T-Pot
Docker
SSH
T-Pot
WireGaurd(in progress)
## Testing
Controlled TCP port scanning was proformed by kali Linux VM against T-Pot VM

Surcata detected the traffic and then displayed and analyzed the attacks through a kibana dashboard
## Results
The T-pot vm successfully detected and recorded activity generated from the TCP port scans made by the Kali linux VM

Events that were generated produced visible security events on the monitoring dashboard and produced the source address, timestamp of the security event, along with the signature of the attack itself. 
![T-Pot Dashboard](screenshots/t-potdashboard.png)
![Suricata Alerts](screenshots/alerts.png)
## Lessons Learned
This lab was able to deliver hands on experience with
    -Linux system administration
    -Virtual networking
    -troubleshooting network configuration
    -Network recconnaissance
    -security event analysis
    -log visualisation
    -docker based security infrastructor
    -honeypot script configuration/troubleshooting
    -VPN configuration (in progress)
    -remote system administration(in progress)