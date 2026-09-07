
# 🚀 Enterprise Network Automation & Security Lab

> A hands-on enterprise network engineering, automation, and security project built using GNS3, Cisco IOS, Ubuntu Linux, Python, Netmiko, Ansible, and Git/GitHub.

## 🏗️ Project Architecture & Automation Workflow
```text
                              INTERNET
                                  |
                           +--------------+
                           |   FIREWALL   |
                           +--------------+
                                  |
                           +--------------+
                           |   HQ ROUTER  |
                           +--------------+
                                  |
                 +----------------+----------------+
                 |                                 |
           HEAD OFFICE                         BRANCH OFFICE
                 |                                 |
          +------+------+                     +----+----+
          |             |                     |         |
         R1             R2                    R3      SWITCH
          |             |                     |         |
       +--+--+       +--+--+                VLANs     USERS
       |     |       |     |                   |
     SW1   SW2     SW3   SW4                USERS
       |     |       |     |
     VLANs VLANs   VLANs VLANs
                 

                         MANAGEMENT NETWORK
                                  |
                                  |
                    +--------------------------+
                    | Ubuntu Automation Server |
                    |          Linux           |
                    +--------------------------+
                                  |
                                  |
                                SSH
                                  |
                 +----------------+----------------+
                 |                |                |
                 |                |                |
                R1               R2               R3
                 |                |                |
             Cisco IOS        Cisco IOS        Cisco IOS


                    AUTOMATION WORKFLOW
                              |
                              v
                     +----------------+
                     | Device         |
                     | Inventory      |
                     +----------------+
                              |
                              v
                       +-------------+
                       | YAML        |
                       | Inventory   |
                       +-------------+
                              |
                              v
                  +-----------------------+
                  | Python / Ansible      |
                  |                       |
                  | Netmiko / Paramiko    |
                  | NAPALM / Scrapli      |
                  +-----------------------+
                              |
                              v
                           SSH
                              |
                              v
                    +-------------------+
                    | Cisco Devices     |
                    | R1 / R2 / R3      |
                    +-------------------+
                              |
                +-------------+-------------+
                |             |             |
                v             v             v
          Configuration    Backup       Health Check
                |             |             |
                v             v             v
             Validate       Git       Network Report
                |             |             |
                +-------------+-------------+
                              |
                              v
                    +-------------------+
                    | Security Audit    |
                    | & Compliance      |
                    +-------------------+
                              |
                              v
                    +-------------------+
                    | Final Report      |
                    +-------------------+

```
## 🎯 Project Objectives
- Build an enterprise-style multi-site network
- Configure Cisco routers and switches
- Implement VLANs and trunking
- Implement inter-VLAN routing
- Configure OSPF
- Configure DHCP, DNS, NAT, and ACLs
- Configure secure SSH management
- Build an Ubuntu Network Automation Server
- Automate Cisco devices using Python
- Automate configuration backups
- Perform network health checks
- Automate configuration deployment
- Validate configuration changes
- Generate network reports
- Use Git/Github for configuration version control
- Introduce Ansible
- Implement network security auditing
- Build security automation

## 🐧 Ubuntu Packages

**Download all packages in Ubuntu Linux Server**
```text
sudo apt install -y \
iproute2 \
iputils-ping \
traceroute \
tracepath \
mtr-tiny \
dnsutils \
net-tools \
curl \
wget \
netcat-openbsd \
tcpdump \
nmap \
openssh-client \
openssh-server \
ssh \
scp \
sftp \
rsync \
ethtool \
bridge-utils \
vlan \
arping \
lsof \

```
## System & Devlopment

**Download all packages in Ubuntu Linux Server**
```text
sudo apt install -y \
htop \
iotop \
tree \
jq \
vim \
nano \
git \
git-lfs \
unzip \
zip \
tar \ 
ca-certificates \
build-essential \
python3 \
python3-pip \
python3-venv \
python3-dev \
python3-setuptools \
python3-wheel \

```
## Monitoring & Security

**Download all packages in Ubuntu Linux Server**
```text
sudo apt install -y \
snmp \ 
snmpd \
chrony \
ufw \
nftables \

```
## 🐍 Python Automation Stack

**Now install Python packages inside python virtual venv**
```text
cd ~/network-automation
source venv/bin/activate

pip install netmiko
pip install paramiko
pip install napalm
pip install scrapli
pip install ncclient
pip install requests
pip install pyyaml
pip install jinja2
pip install textfsm
pip install ntc-templates
pip install ttp
pip install ansible

```

## 🌐 Networking Technologies
- IPv4
- Subnetting
- VLAN
- 802.1Q
- Trunking
- Inter-VLAN Routing
- Static Routing
- OSPF
- DHCP
- DNS
- NAT
- ACL
- STP
- EtherChannel
- SSH
- ARP
- ICMP
- TCP/UDP
- SNMP
- NTP

## Automation Features
**Configuration Backup**

```text

Cisco Device
     |
     | SSH
     v
Ubuntu Automation Server
     |
     v
Running Configuration
     |
     v
Backup
     |
     v
Git / GitHub

```
## Network Health Check
> The automation system will collect:
```text
Hostname
IOS Version
Uptime
CPU
Memory
Interface Status
Interface Errors
IP Addresses
Routing Table
OSPF Neighbors
ARP Table
VLAN Information

```

## Configuration Deployment

```text
Inventory
    ↓
Jinja2 Template
    ↓
Generate Configuration
    ↓
Backup
    ↓
SSH
    ↓
Deploy
    ↓
Verify
    ↓
Save
    ↓
Report

```

## Network Security
Planned security automation:
- SSH security auditing
- Telnet detection
- ACL auditing
- VLAN auditing
- Unauthorized VLAN detection
- Unused port detection
- Interface security checks
- Privileged user auditing
- Firewall auditing
- Nmap port auditing
- SNMP security checks
- Configuration compliance
- Security baseline verification
- Automated security reports

## Project Structure
```text
network-automation/
│
├── README.md
├── requirements.txt
├── .gitignore
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
└── tests/

```

## Skills Demonstrated
**Network Engineering**
- Cisco IOS
- Routing & Switching
- VLANs
- OSPF
- DHCP
- DNS
- NAT
- ACL
- STP
- EtherChannel
- SSH
- Network Troubleshooting

**Linux**
- Ubuntu Administration
- Linux Networking
- Bash
- SSH
- systemd
- Netplan
- NetworkManager
- Firewall Management
- Packet Capture

**Automation**
- Python
- Netmiko
- Paramiko
- NAPALM
- NETCONF
- Scrapli
- Jinja2
- YAML
- TextFSM
- Ansible

**Security**
- Nmap
- Wireshark
- tcpdump
- SNMP
- Firewall
- SSH Hardening
- Security Auditing
- Configuration Compliance









