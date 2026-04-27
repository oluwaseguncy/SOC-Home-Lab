# SOC Home Lab

## Overview
Building a hands-on SOC analyst home lab to develop real-world security operations skills.

## Environment
- Host OS: Windows
- Virtualization: Oracle VirtualBox
- Guest OS: Ubuntu Server 24.04 LTS (50GB disk)
- SIEM: Splunk Enterprise 10.2.1

## Progress
### Day 1
- Installed VirtualBox on Windows host
- Created Ubuntu Server 24.04 LTS VM
- Configured NAT network with port forwarding

### Day 2
- Installed Splunk Enterprise 10.2.1
- Configured shared folders between Windows and Ubuntu
- Accessed Splunk web interface at http://127.0.0.1:8000

### Day 3
- Loaded Splunk tutorial dataset
- Ran first SPL searches
- Investigated brute force attack logs (33,253 failed password events)

## Skills Developed
- Linux command line
- VirtualBox VM management
- Splunk SPL search language
- Log analysis










## Distribited SSH Brute Force Investigation

### Overview
Investigated distributed SSH Brute Force attack using SPL rex command to extract attacking IPs from raw log data.

### SPL Query Used
index=main sourcetype="secure-2""Failed password"
|rex"from (?<ip>[\d.]+)port"
|stats dc(ip) as total_attackers
