
🚀 Enterprise Network Automation & Security Lab

A hands-on enterprise-style network engineering project built with GNS3, Cisco IOS, Ubuntu Linux, Python, Netmiko, Ansible, Git/GitHub, and security tools.

🎯 Project Goals

Build a multi-site enterprise network in GNS3

Configure Cisco routers and switches

Implement VLANs, inter-VLAN routing and OSPF

Configure secure SSH management

Use Ubuntu as the central network automation server

Automate Cisco devices with Python and Netmiko

Automate configuration backups

Perform device health checks

Deploy and validate configurations

Generate network reports

Track configurations with Git/GitHub

Introduce Ansible automation

Build network security auditing and compliance checks

🏗️ Planned Architecture

                         INTERNET
                            |
                     +--------------+
                     |   Firewall   |
                     +--------------+
                            |
                       +---------+
                       | HQ Edge |
                       | Router  |
                       +---------+
                            |
              +-------------+-------------+
              |                           |
          HQ Network                 Branch Network
              |                           |
       +------+------+                +----+----+
       |             |                |         |
      R1/R2       Switches            R3      Switch
       |             |                |         |
     VLANs         Users             VLANs     Users

                 MANAGEMENT / AUTOMATION
                         |
              +----------------------+
              | Ubuntu Automation VM |
              +----------------------+
                         |
                 SSH to Cisco Devices

🖥️ Lab Environment

Technology

Purpose

Windows

Host OS

Oracle VirtualBox

Virtualization

GNS3

Network simulation

GNS3 VM

GNS3 server/appliances

Cisco IOS

Routers and switches

Ubuntu Linux

Automation server

Wireshark

Packet analysis

🐧 Ubuntu Packages Installed

Networking

iproute2
iputils-ping
traceroute
tracepath
mtr-tiny
dnsutils
net-tools
curl
wget
netcat-openbsd
tcpdump
nmap
openssh-client
openssh-server
ssh
scp
sftp
rsync
ethtool
bridge-utils
vlan
arping
lsof

System / Development

htop
iotop
tree
jq
vim
nano
git
git-lfs
unzip
zip
tar
ca-certificates
build-essential
python3
python3-pip
python3-venv
python3-dev
python3-setuptools
python3-wheel

Monitoring / Security

snmp
snmpd
snmp-mibs-downloader
ntp
chrony
ufw
nftables

🐍 Python Network Automation Stack

Python
Netmiko
Paramiko
NAPALM
NCClient
Scrapli
Requests
PyYAML
Jinja2
TextFSM
ntc-templates
TTP
ttp-templates
Ansible

Technology

Purpose

Python

Automation logic

Netmiko

Cisco/device SSH automation

Paramiko

SSH automation

NAPALM

Multi-vendor automation

NCClient

NETCONF

Scrapli

Network device connections

PyYAML

YAML inventory

Jinja2

Configuration templates

TextFSM

CLI output parsing

ntc-templates

Network command parsing

Requests

REST/API automation

Ansible

Infrastructure/network automation

🌐 Networking Technologies

IPv4 addressing and subnetting

VLANs / 802.1Q

Access and trunk ports

Inter-VLAN routing

Static routing

OSPF

DHCP

DNS

NAT

ACLs

SSH

EtherChannel

STP

SNMP

NTP

ARP

ICMP

TCP/UDP

Network monitoring

Packet analysis

Network troubleshooting

🔐 Network Security

Planned security capabilities:

SSH-only device management

Telnet detection

ACL auditing

VLAN auditing

Unauthorized VLAN detection

Unused/disabled interface checks

Privileged account auditing

Firewall rules

UFW/nftables

Port auditing with Nmap

SNMP security checks

Configuration compliance

Security baseline verification

Automated security reports

🤖 Automation Features

1. Device Inventory

devices:
  - name: R1
    host: 10.10.10.1
    device_type: cisco_ios

  - name: R2
    host: 10.10.10.2
    device_type: cisco_ios

  - name: R3
    host: 10.20.20.1
    device_type: cisco_ios

2. Automated Backups

Cisco Device
     |
     | SSH
     v
Ubuntu Automation Server
     |
     v
running-config
     |
     v
backups/
     |
     v
Git

3. Network Health Checks

The automation system will collect:

Hostname
IOS Version
Uptime
CPU
Memory
Interface Status
IP Addresses
Routing Table
OSPF Neighbors
ARP/Neighbor Table
VLAN Information
Interface Errors

4. Automated Configuration Deployment

Inventory
   ↓
Jinja2 Template
   ↓
Backup
   ↓
Connect
   ↓
Apply Configuration
   ↓
Verify
   ↓
Save
   ↓
Generate Report

📊 Reporting

Planned reports:

reports/
├── health/
├── security/
├── backups/
└── compliance/

Reports will include device availability, interface status, IP addressing, routing, OSPF neighbors, backups, configuration changes and security findings.

📁 Repository Structure

network-automation/
│
├── inventory/
│   ├── devices.yml
│   └── groups.yml
│
├── scripts/
│   ├── backup.py
│   ├── health_check.py
│   ├── config_deploy.py
│   ├── ospf_check.py
│   └── security_audit.py
│
├── configs/
│   ├── templates/
│   └── generated/
│
├── backups/
├── reports/
│   ├── health/
│   ├── security/
│   └── compliance/
│
├── logs/
│
├── ansible/
│   ├── inventory/
│   ├── playbooks/
│   ├── roles/
│   └── group_vars/
│
├── tests/
├── requirements.txt
├── .gitignore
└── README.md

🔧 Important Linux Network Commands

ip addr
ip -br addr
ip link
ip route
ip route get 8.8.8.8
ip neigh
ping
traceroute
tracepath
mtr
dig
nslookup
ss
lsof
tcpdump
nmap
ethtool
nmcli
resolvectl
systemctl
journalctl
curl
wget
nc
ssh
scp
sftp
rsync

📡 SSH Management

SSH is the primary management protocol between Ubuntu and Cisco devices.

ssh admin@10.10.10.1
ssh -vvv admin@10.10.10.1

Check the local SSH service:

sudo systemctl enable --now ssh
sudo systemctl status ssh
sudo ss -lntp | grep :22

📦 Packet Analysis

Using tcpdump and Wireshark to inspect:

ARP

ICMP

DNS

DHCP

TCP

UDP

SSH

HTTP/HTTPS

VLAN traffic

Examples:

sudo tcpdump -i any -nn
sudo tcpdump -i any -nn port 22
sudo tcpdump -i any -nn icmp
sudo tcpdump -i any -nn 'port 67 or port 68'

🧪 Development Roadmap

Phase 1 — Linux

Linux CLI

Filesystem

Permissions

Processes

Services

Package management

Linux networking

Phase 2 — Networking

IP addressing

VLANs

Routing

OSPF

DHCP

DNS

NAT

ACL

SSH

Phase 3 — GNS3

Build HQ

Build Branch

Configure Cisco routers

Configure switches

Establish routing

Verify connectivity

Phase 4 — SSH

Ubuntu → SSH → Cisco R1
Ubuntu → SSH → Cisco R2
Ubuntu → SSH → Cisco R3

Phase 5 — Python

Python fundamentals

Files

Functions

Loops

Exceptions

YAML

JSON

APIs

Phase 6 — Netmiko

Connect to devices

Execute show commands

Collect output

Save output

Configuration backup

Configuration deployment

Phase 7 — Advanced Automation

Jinja2

TextFSM

NAPALM

NETCONF

REST APIs

Scrapli

Phase 8 — Git/GitHub

Version control

Branches

Commits

Configuration history

Automation code management

Phase 9 — Ansible

Inventory

Playbooks

Variables

Templates

Roles

Cisco automation

Phase 10 — Security Automation

Security auditing

Compliance checks

ACL auditing

VLAN auditing

SSH security

Port auditing

Automated security reports

🛠️ Technology Stack

                    PROJECT
                       |
        +--------------+--------------+
        |              |              |
     Networking     Automation      Security
        |              |              |
      Cisco          Python         Linux
      GNS3           Netmiko        Firewall
      OSPF           Ansible        Nmap
      VLAN           Paramiko       Wireshark
      SSH            NAPALM         SNMP
      DHCP           NETCONF        ACL
      DNS            Jinja2
                     Git

Networking

Cisco IOS, GNS3, VLAN, OSPF, DHCP, DNS, NAT, ACL, STP, EtherChannel, SSH

Linux

Ubuntu, Bash, systemd, iproute2, NetworkManager, Netplan, nftables, UFW

Automation

Python, Netmiko, Paramiko, NAPALM, Scrapli, NCClient, Ansible, Jinja2, YAML, JSON, TextFSM

DevOps

Git, GitHub, configuration version control, logging, automated reports

Security

Wireshark, tcpdump, Nmap, SNMP, firewall, SSH hardening, security auditing

Virtualization

Oracle VirtualBox, GNS3 VM, Ubuntu VM

📌 Project Status

[✓] Ubuntu Network Automation VM
[✓] Python environment
[✓] Linux networking tools
[✓] SSH server
[✓] Git
[✓] GNS3
[✓] GNS3 VM
[ ] Cisco topology
[ ] Cisco SSH connectivity
[ ] Netmiko automation
[ ] Automated backups
[ ] Health monitoring
[ ] Configuration deployment
[ ] Jinja2 templates
[ ] Git automation
[ ] Ansible automation
[ ] Security auditing
[ ] Automated reporting

🎓 Skills Demonstrated

Linux Administration

Network Troubleshooting

Cisco IOS Configuration

Routing & Switching

OSPF

VLANs

Network Security

SSH

Python Programming

Network Automation

Configuration Management

Git/GitHub

Ansible

NETCONF/API concepts

Monitoring

Packet Analysis

Security Auditing

⚠️ Disclaimer

This project is intended for educational, testing, and authorized lab environments.

Cisco images and other vendor software should be obtained through legitimate/licensed sources.

Never run automation, scanning, or configuration changes against networks or devices without authorization.

🚀 Future Improvements

Multi-vendor automation

Automated topology discovery

Configuration compliance

Automated rollback

Scheduled backups

Email/notification alerts

Web dashboard

REST API integration

Prometheus/Grafana monitoring

CI/CD for network configuration

Automated security remediation

Containerized automation environment

👨‍💻 Project Focus

Network Engineering → Network Automation → Network Security

The long-term goal is to build a production-style automation platform capable of managing, monitoring, validating, and securing enterprise network infrastructure.

🚧 Active Development
