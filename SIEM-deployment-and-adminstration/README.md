# SIEM Deployment & Adminstration

## Objective
To demonstrate the deployment, configuration, validation, administration, and troubleshooting of a SIEM platform.

## Architecture
```
                         Host Machine
                              │
                    Oracle VirtualBox
                              │
        ┌─────────────────────┼─────────────────────┐
        │                     │                     │
        ▼                     ▼                     ▼
   Wazuh-SOC             WindowsSOC            Kali-Linux
   Ubuntu 24.04           Windows 10             Kali
        │                     │
        │                     │
        │              Wazuh Agent
        │                     │
        └──────── Host-Only Network ───────────────┘
                    192.168.213.0/24
```


## Phase 1 : Deployment of the system
### Wazuh Server 

Hostname: wazuh-soc
IP:       192.168.213.104
OS:       Ubuntu Server 24.04
RAM:      8 GB
CPU:      4
Disk:     ~58 GB usable root filesystem

### Components

Wazuh Manager
Wazuh Indexer
Wazuh Dashboard

### Windows endpoint
Hostname: WindowsSOC
IP:       192.168.213.102
OS:       Windows 10
Agent:    Wazuh Agent 4.14.7

### Kali 
Purpose: Attack simulation / adversary emulation

## Phase 2 : Validation
### Validate the Wazuh server
- Check hostname
- Check IP
- Check disk, RAM, CPU

<img width="473" height="147" alt="image" src="https://github.com/user-attachments/assets/20028a25-a220-406d-9d84-85dd9ad36025" />

- Validate the state of 3 core SIEM components : wazuh-manager, wazuh-indexer, wazuh-dashboard
- Validate the agent

<img width="449" height="123" alt="image" src="https://github.com/user-attachments/assets/a579b3f5-9e10-455f-88cf-48d332c146df" />

- Validate the dashboard

<img width="947" height="503" alt="image" src="https://github.com/user-attachments/assets/0963de1b-4b48-449a-8bf6-fdbb9225d8b4" />

