# Wazuh + Suricata SOC Lab 🛡️

## Overview
This project involved deploying a comprehensive Security Operations Center (SOC) lab. I integrated **Wazuh (EDR)** with **Suricata (IDS)** and the **VirusTotal API** to create an automated detection and response system.

## 🏗️ Architecture
- **Wazuh Manager:** Centralized alerts and log analysis.
- **Suricata:** Network Intrusion Detection (IDS) monitoring traffic.
- **Agents:** (List the OS you monitored, e.g., Ubuntu/Windows).
- **Integrations:** VirusTotal for automated file integrity checking.

## 🛠️ Implementation Steps
1. **Server Deployment:** Installed the Wazuh Indexer, Server, and Dashboard. 
2. **IDS Configuration:** Deployed Suricata and configured it to log into the Wazuh manager.
3. **Threat Intelligence:** Configured `ossec.conf` to pull from VirusTotal API for real-time file analysis.
4. **Troubleshooting:** (Briefly mention how you fixed the indexer communication issues to get them to "Green" status).

## 📊 Verification
*(This is where you'll upload screenshots later showing the Wazuh dashboard with active alerts and Suricata logs).*
