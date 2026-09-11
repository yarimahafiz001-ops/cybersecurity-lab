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
              │   10.0.0.2/24     │
              └───────────────────┘
                        │
          Future Target VMs: .3 – .99
