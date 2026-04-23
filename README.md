# Active Directory Home Lab

## Overview

I built small Active Directory lab built to simulate a basic enterprise IT environment using Windows Server 2022 and Windows 11 virtual machines. The goal was to gain hands-on experience with core IT support and systems administration tasks.

Using Hyper-V Manager, a Windows Server 2022 is configured as a Domain Controller (DC01) with Active Directory Domain Services and DNS installed. A Windows 11 client machine (CLIENT01) was then connected to the same vnet and joined to the domain. The environment was used to practice common IT troubleshooting scenarios such as network misconfigurations, domain join issues, user and group management, login issues, network issues, and more

---

## Lab Architecture

- **Domain Controller:** DC01 (Windows Server 2022)
- **Client Machine:** CLIENT01 (Windows 11)
- **Domain Name:** lab.local
- **Network Type:** Private Vnet
- **IP Scheme:**
  - DC01: 192.168.10.10
  - CLIENT01: 192.168.10.20
- **DNS Server:** DC01 (192.168.10.10)

---

## Setup

### 1. Virtual Machine Configuration
- Created two VMs (DC01 and CLIENT01)
- Installed Windows Server on DC01
- Installed Windows 11 on CLIENT01
- Connected both to the same vnet

---

### 2. DC01 Setup
- Installed **Active Directory Domain Services**
- Promoted server to Domain Controller
- Created new forest: `lab.local`
- Installed and configured DNS role

---

### 3. Network & DNS Configuration
- Assigned static IP to DC01
- Configured DC01 as DNS server
- Set CLIENT01 DNS to DC01 IP address
- Verified internal name resolution

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/12d736df-1438-42a0-81c5-4e4693494f6c" />

---

### 4. Active Directory Configuration
- Created Organizational Units (OUs):
  - HR
  - IT
  - Sales
- Created domain users within each OU
- Created security groups for each department
- Assigned users to appropriate groups

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/5cd6659f-9517-4eb2-a4f3-8cf2abf39754" />


---

### 5. Domain Join (CLIENT01)
- Joined Windows 11 client to `lab.local` domain
- Verified domain authentication
- Logged in using domain credentials

---

## Setup Troubleshooting

- I resolved a VM boot issue by researching known problems. The boot order was incorrect, so I re-ordered it so that that the DVD drive would be read first. This is where the Windows 11 iso file would be read.
