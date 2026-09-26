# SIEM Deployment 

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
````
Hostname: wazuh-soc
IP:       192.168.213.104
OS:       Ubuntu Server 24.04
RAM:      8 GB
CPU:      4
Disk:     ~58 GB usable root filesystem
````
### Components
````
Wazuh Manager
Wazuh Indexer
Wazuh Dashboard
````
### Windows endpoint
````
Hostname: WindowsSOC
IP:       192.168.213.102
OS:       Windows 10
Agent:    Wazuh Agent 4.14.7
````
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

# SIEM Administration
## Phase 1 : Service Management
#### Step 1: Service Configuration
Confirms that all three core Wazuh services are configured for automatic startup and currently operational.
````
| Wazuh component | Boot enabled | Current state |
| --------------- | ------------ | ------------- |
| Wazuh Manager   | `enabled`    | `active`      |
| Wazuh Indexer   | `enabled`    | `active`      |
| Wazuh Dashboard | `enabled`    | `active`      |
````
#### Step 2: Controlled service restart
Restart test was successful

<img width="598" height="322" alt="image" src="https://github.com/user-attachments/assets/f1f5d281-ee66-4013-939d-09391adf9d72" />

#### Step 3: Verify the endpoint after the restart
To confirm that WindowsSOC (Agent 003) is still connected after the Manager restart.

output: ````ID: 003, Name: WindowsSOC, IP: any, Active````

#### Step 4: Check service logs
<img width="699" height="431" alt="image" src="https://github.com/user-attachments/assets/446723cb-a593-48e8-baa6-339e645b1ddb" />

#### Step 5: Check all three services after the restart
````
sudo systemctl is-active wazuh-manager
sudo systemctl is-active wazuh-indexer
sudo systemctl is-active wazuh-dashboard
````
and all successfully returned active status
## Phase 2 : Agent Administration
## Phase 3 : SIEM Health & Capacity Monitoring
## Phase 4 : Configuration Backup & Recovery
## Phase 5 : Administration Troubleshooting Case


