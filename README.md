# enterprise-soc-purple-team-lab
A hands-on cybersecurity lab focused on SIEM monitoring, endpoint telemetry, detection engineering, threat hunting, incident investigation, and MITRE ATT&amp;CK-based Purple Team exercises using Wazuh, Windows, and Kali Linux.

## Lab Architecture

                    PURPLE TEAM SOC LAB
                           │
          ┌────────────────┴────────────────┐
          │                                 │
     OFFENSIVE SIDE                    DEFENSIVE SIDE
          │                                 │
    Kali Linux                         Wazuh-SOC
    Recon / Attack                         │
          │                         ┌───────┴────────┐
          ▼                         │                │
     WindowsSOC ─────────────────► Manager       Dashboard
     Target + Agent                    │
          │                            │
          └────────────────────────────┤
                                       ▼
                                  Detection /
                                  Investigation

## Repo structure
 ```
enterprise-soc-purple-team-lab/
│
├── README.md
│
├── architecture/
│   ├── network-diagram.png
│   └── lab-topology.md
│
├── 01-endpoint-monitoring/
│
├── 02-network-reconnaissance/
│
├── 03-authentication-attacks/
│
├── 04-powershell-detection/
│
├── 05-file-integrity-monitoring/
│
├── 06-process-monitoring/
│
├── 07-threat-detection/
│
├── 08-mitre-attack/
│
├── 09-detection-engineering/
│
├── 10-incident-investigation/
│
└── reports/
    ├── incident-reports/
    └── purple-team-assessments/

```

## Phase 1 — SIEM Deployment & Administration
```
├── 1.1 Architecture & Requirements
├── 1.2 Wazuh Deployment
├── 1.3 Network & Service Validation
├── 1.4 Agent Administration
├── 1.5 SIEM Health Monitoring
└── 1.6 Documentation & Evidence
```
