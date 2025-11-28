# Active-Directory-Detection-Lab-using-Splunk-SIEM
A fully deployed detection environment simulating enterprise Windows infrastructure, Active Directory authentication logs, Sysmon telemetry, and Splunk Enterprise SIEM for threat detection and alerting.

📌 Project Overview

This project builds a realistic Windows enterprise domain inside AWS, integrates Splunk SIEM, and generates real security telemetry for analysis and threat detection.

The goal:
✔ Learn Active Directory
✔ Analyze Windows logs
✔ Build Splunk detections
✔ Understand attacker behaviors
✔ Practice SOC investigations

🎯 Objectives

Deploy a Windows Domain Controller (AD DS + DNS)

Deploy a Windows Client Machine

Install Splunk Enterprise on Ubuntu

Install Splunk Universal Forwarder on AD + Client

Configure log ingestion + Sysmon

Generate detection use-cases (failed logins, RDP abuse, PowerShell misuse)

Build Splunk queries to detect malicious actions

🧠 Skills Learned

Active Directory administration

SIEM deployment & log ingestion

Windows Event Log analysis

AWS security & networking

Threat detection engineering

Sysmon configuration + analysis

SOC investigation workflows

🛠 Tools Used

Splunk Enterprise (SIEM)

Splunk Universal Forwarder

Windows Server 2022 (AD DS)

Windows 10/11 Client

Sysmon v14

AWS EC2 + Security Groups

PowerShell / CMD

📡 Architecture Diagram
                 ┌────────────────────────┐
                 │ Splunk Enterprise SIEM │
                 │   (Ubuntu, port 9997)   │
                 └─────────────▲──────────┘
                               │
     ┌─────────────────────────┼──────────────────────────┐
     │                         │                          │
     ▼                         ▼                          ▼
┌──────────────┐       ┌──────────────┐          ┌─────────────────┐
│ Windows AD    │       │ Windows Client│          │ Sysmon Logs     │
│ Domain Ctrl   │──────▶│ Workstation  │─────────▶│ Security Logs   │
└──────────────┘       └──────────────┘          └─────────────────┘

☁️ AWS Environment Setup
Security Group Rules

The following rules were required for domain & client connectivity:

Type	Protocol	Port	Purpose
All Traffic	All	All	Internal VPC communication
RDP	TCP	3389	Remote Desktop
All ICMP IPv4	ICMP	All	Ping / Troubleshooting

📸 AWS Security Group:
/screenshots/sg-rules.png

Network Connectivity Testing

Once ICMP was enabled, the Domain Controller and Client successfully communicated via ping.


🏰 Active Directory Setup
Domain Name: MyADProject.local
Steps Completed

✔ Installed AD DS
✔ Promoted server to Domain Controller
✔ Configured DNS
✔ Created Organization Units
✔ Created test user: bsmith
✔ Joined Windows client to domain
