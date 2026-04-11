# Wazuh + Suricata SOC Lab 🛡️

## Overview
This project involved deploying a comprehensive Security Operations Center (SOC) lab. I integrated **Wazuh (EDR)** with **Suricata (IDS)** and the **VirusTotal API** to create an automated detection and response system.

## 🏗️ Architecture
- **Wazuh Manager:** Centralized alerts and log analysis.
- **Suricata:** Network Intrusion Detection (IDS) monitoring traffic.
- **Agents:** (Kali-Linux).
- **Integrations:** VirusTotal for automated file integrity checking.

## 🛠️ Implementation Steps
1. **Server Deployment:** Installed the Wazuh Indexer, Server, and Dashboard. 
2. **IDS Configuration:** Deployed Suricata and configured it to log into the Wazuh manager.
3. **Threat Intelligence:** Configured [ossec.conf](./ossec.conf) to pull from VirusTotal API for real-time file analysis.
4. **Active Response Automation:** Developed a custom Bash script to parse JSON [Active-Resposne](./remove-threat.sh) alert data and execute real-time threat remediation via automated file deletion.

## 🔧 Troubleshooting & Engineering Hurdles

During the deployment, I encountered several critical blockers that required system-level optimization:

- **Indexer Timeout & Startup Failures:** The Wazuh Indexer initially failed to start due to service timeouts. I diagnosed this as a resource contention issue where the service was attempting to initialize before the system had allocated sufficient resources.
- **RAM Optimization:** Running the full stack (Indexer, Manager, Dashboard) pushed the hardware limits. I had to optimize JVM heap sizes and adjust memory allocation to prevent the OOM (Out of Memory) killer from terminating the Indexer process.
- **Service Dependency Mapping:** I resolved communication gaps between the indexer and the manager by verifying listener ports and ensuring the security certificates were correctly mapped despite the initial resource-induced lag.

**Result:** Achieved a stable "Green" health status across all nodes.

## 📊 Verification
![IMG_0954](https://github.com/user-attachments/assets/49070057-0700-4b6f-863c-b2e886631bb7)

