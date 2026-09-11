# 🔐 Cybersecurity & Penetration Testing Lab

A controlled virtual cybersecurity laboratory built with **VirtualBox and Kali Linux** for learning network security, reconnaissance, vulnerability assessment, and authorized penetration-testing techniques.

## 📌 Project Overview

This project documents the setup of an isolated cybersecurity laboratory environment designed for practical security training and experimentation.

The lab provides a safe foundation for future exercises involving network reconnaissance, vulnerability assessment, web security testing, packet analysis, and controlled penetration testing.

## 🎯 Objectives

- Build a repeatable cybersecurity laboratory environment.
- Configure Kali Linux for security assessment activities.
- Configure a dedicated VirtualBox NAT Network.
- Practice IPv4 networking and troubleshooting.
- Verify connectivity, routing, and DNS resolution.
- Validate security tools such as Nmap.
- Create a clean VM snapshot for recovery.
- Prepare the environment for future vulnerable target machines.

## 🏗️ Lab Environment

| Component | Configuration |
|---|---|
| Host OS | Windows 10 |
| Processor | Intel Core i7 |
| Host RAM | 8 GB |
| Hypervisor | VirtualBox 7.2 |
| Security OS | Kali Linux 2026.2 |
| Kali RAM | 2048 MB |
| Network | NAT Network |
| Network Name | NatNetwork |
| Network Address | 10.0.0.0/24 |
| Kali IP | 10.0.0.2/24 |
| Gateway | 10.0.0.1 |
| DNS | 8.8.8.8 |
| DHCP | Enabled |
| IPv6 | Disabled |

## 🌐 Network Architecture

The laboratory uses a VirtualBox NAT Network named `NatNetwork`.

```text
                    INTERNET
                        │
                        │
              ┌─────────▼─────────┐
              │    Windows 10     │
              │ Intel Core i7     │
              │      8 GB RAM     │
              └─────────┬─────────┘
                        │
                 VirtualBox 7.2
                        │
              ┌─────────▼─────────┐
              │    NatNetwork     │
              │   10.0.0.0/24     │
              │   Gateway: .1     │
              └─────────┬─────────┘
                        │
              ┌─────────▼─────────┐
              │    Kali Linux     │
              │      2026.2       │
              │   10.0.0.2/24
│
        🧰 Tools Used
Kali Linux — Cybersecurity testing platform
VirtualBox — Virtualization and VM management
Nmap — Network discovery and port scanning
NetworkManager / nmcli — Linux network configuration
ping — Network connectivity testing
ip — Network interface and routing inspection
nslookup — DNS resolution testing
7-Zip — VM archive extraction
⚙️ Setup Procedure
1. Install 7-Zip
7-Zip was used to extract the Kali Linux virtual-machine package and prepare the VM files for import.
2. Install VirtualBox
VirtualBox was installed as the virtualization platform used to host the cybersecurity laboratory.
3. Create the NAT Network
A dedicated NAT Network named:
NatNetwork
was configured with:
IPv4 Prefix: 10.0.0.0/24
DHCP: Enabled
IPv6: Disabled
4. Import Kali Linux
The Kali Linux 2026.2 virtual machine was imported into VirtualBox.
Configuration:
RAM: 2048 MB
Network Adapter: Adapter 1
Network: NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
A shared folder was also configured for controlled file transfer.
5. Configure Kali Networking
The Kali VM was configured with:
IP Address:     10.0.0.2
Subnet Mask:    255.255.255.0
Gateway:        10.0.0.1
DNS:            8.8.8.8
🔎 Lab Verification
The following commands were used to verify the environment:
ip a
ip route
ping 10.0.0.1
ping 8.8.8.8
nslookup networkwalks.com
nmap --version
Expected Results
Kali displays the expected IPv4 address.
Correct default gateway and route are displayed.
Gateway connectivity is successful where permitted.
Internet connectivity is available.
DNS resolution works correctly.
Nmap is installed and available.
🐞 Troubleshooting
Static IPv4 Connectivity Issue
A static IPv4 configuration may cause connectivity problems depending on the Kali Linux and NetworkManager configuration.
A workaround used during the lab was:
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
Before modifying a connection, check the actual connection name:
nmcli connection show
The connection name may differ between systems.
Virtualization Error
The Kali VM initially encountered a hardware virtualization issue.
The solution was to:
Restart the computer.
Enter BIOS/UEFI.
Locate the virtualization setting.
Enable Intel VT-x / hardware virtualization.
Save the configuration.
Restart the computer.
Start the Kali VM again.
🔄 Snapshot & Recovery
A clean snapshot was created after completing the initial laboratory configuration.
Snapshot: Clean Kali - Network Setup
This snapshot provides a known-good recovery point before performing potentially disruptive cybersecurity experiments.
🧠 Key Skills Demonstrated
Virtual machine deployment
Linux system administration
IPv4 addressing
Network configuration
Routing and DNS troubleshooting
Virtual networking
Cybersecurity lab architecture
Security-tool validation
Technical documentation
Troubleshooting
🚀 Future Improvements
The laboratory will be expanded with:
Intentionally vulnerable Linux target VM
Vulnerable Windows target VM
Vulnerable web applications
Network reconnaissance exercises
Controlled Nmap scanning
Vulnerability assessments
Wireshark packet analysis
Web security testing
Controlled exploitation scenarios
Security assessment reports
Security automation with Python and shell scripting
🔐 Security & Ethical Use
This laboratory is intended strictly for education, authorized security testing, and cybersecurity research.
All scanning, vulnerability assessment, and penetration-testing activities must be performed only against:
Systems you own
Systems specifically created for testing
Systems for which you have explicit authorization
Never use these techniques against unauthorized systems, networks, websites, or devices.
📁 Repository Structure
cybersecurity-lab/
│
├── README.md
├── WEEK_1_PROJECT_HAMZA_AHMAD.pdf
│
├── documentation/
│   ├── lab-architecture.md
│   ├── setup-procedure.md
│   ├── troubleshooting.md
│   └── verification.md
│
├── screenshots/
│
└── diagrams/
    └── lab-architecture.png
📚 Resources
7-Zip
VirtualBox
Kali Linux
Nmap
📌 Project Information
Program: Cybersecurity at Networkwalks
Week: 01
Project: Cybersecurity & Penetration Testing Lab Setup
Focus: Virtualization, Linux Networking & Cybersecurity Lab Architecture
Platform: VirtualBox + Kali Linux
👨‍💻 Author
Hamza Ahmad
Computer Science Graduate | Cybersecurity Enthusiast
Areas of Interest:
Cybersecurity
Ethical Hacking
Network Security
Vulnerability Assessment
Information Technology
Security Research
⭐ Project Status
Completed — Initial Lab Setup
The laboratory is ready for future authorized cybersecurity exercises and additional target-machine deployments.      └───────────────────┘
                        │
          Future Target VMs: .3 – .99

