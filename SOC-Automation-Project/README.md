# SOC Automation Project: Wazuh → Shuffle → TheHive

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Objectives](#objectives)  
3. [Environment Setup](#environment-setup)  
4. [Project Steps](#project-steps)  

   * [Part 1: Architecture Diagram](#part-1-architecture-diagram)  
   * [Part 2: Windows Client & Wazuh Agent](#part-2-windows-client--wazuh-agent)  
   * [Part 3: Wazuh Manager Setup](#part-3-wazuh-manager-setup)  
   * [Part 4: Shuffle SOAR Integration](#part-4-shuffle-soar-integration)  
   * [Part 5: TheHive Integration](#part-5-thehive-integration)  
   * [Part 6: Alerts & Playbooks](#part-6-alerts--playbooks)  
5. [Screenshots](#screenshots)  
6. [Reflection & Lessons Learned](#reflection--lessons-learned)  
7. [Future Enhancements](#future-enhancements)  

---

## Project Overview  

This project demonstrates a full **SOC automation workflow** where:  

* A **Windows 10 client with Wazuh Agent** detects suspicious activity.  
* Events are sent to the **Wazuh Manager** for analysis.  
* Alerts are forwarded to **Shuffle SOAR** for automation and enrichment.  
* Shuffle uses **threat intelligence sources** (e.g., VirusTotal) to add context.  
* Enriched alerts are sent to **TheHive** where new cases are created.  
* SOC analysts are **notified via email** for immediate response.  

**Technologies Used:** Windows 10, Ubuntu Server, Wazuh, Shuffle SOAR, TheHive, VirusTotal.  

---

## Objectives  

* Deploy Wazuh Agent on Windows to monitor system activity.  
* Set up Wazuh Manager on Ubuntu for centralized alerting.  
* Configure Shuffle SOAR to enrich alerts with threat intelligence.  
* Automate forwarding of enriched alerts to TheHive.  
* Ensure SOC analysts receive real-time notifications.  

---

## Environment Setup  

* **Windows 10** → Client with Wazuh Agent.  
* **Ubuntu Server** → Wazuh Manager.  
* **Shuffle SOAR** → Automation, enrichment, and workflows.  
* **TheHive** → Incident and case management.  
* **VirusTotal** → Threat intelligence enrichment.  

Networking: Ensure connectivity between client, Wazuh Manager, Shuffle, and TheHive.  
Basic firewall rules: Open required ports for Wazuh (1514/1515), Shuffle (webhook), and TheHive API.  

---

## Project Steps  

### Part 1: Architecture Diagram  

* Create a diagram of the SOC automation workflow showing:  
  * Windows Client (Wazuh Agent)  
  * Wazuh Manager (Ubuntu)  
  * Shuffle SOAR  
  * TheHive  
  * Threat Intelligence (VirusTotal)  
* Store diagram in: `01-Architecture-Diagram/SOC-Automation.png`  

### Part 2: Windows Client & Wazuh Agent  

* Install and configure Wazuh Agent on Windows.  
* Point the agent to Wazuh Manager IP.  
* Verify that logs and alerts are being forwarded successfully.  
* Reference: `02-Windows-Client-Wazuh-Agent/README.md`  

### Part 3: Wazuh Manager Setup  

* Install Wazuh Manager on Ubuntu.  
* Configure agent registration and communication.  
* Define rules for suspicious activities (failed logins, suspicious PowerShell).  
* Forward alerts to Shuffle for further automation.  
* Reference: `03-Wazuh-Manager-Setup/README.md`  

### Part 4: Shuffle SOAR Integration  

* Connect Wazuh alerts to Shuffle using webhook.  
* Enrich alerts with VirusTotal and other intelligence feeds.  
* Automate workflows for IP, hash, and domain lookups.  
* Reference: `04-Shuffle-SOAR-Integration/README.md`  

### Part 5: TheHive Integration  

* Configure Shuffle to forward enriched alerts to TheHive.  
* Auto-create cases for high-severity alerts.  
* Assign cases to SOC analysts for investigation.  
* Enable notifications via email or Slack.  
* Reference: `05-TheHive-Integration/README.md`  

### Part 6: Alerts & Playbooks  

* Create and document automation playbooks in Shuffle.  
* Test scenarios: failed login, suspicious command execution, malware detection.  
* Capture screenshots of alert flow from Wazuh → Shuffle → TheHive.  
* Store in: `06-Alerts-and-Playbooks/`  

---

## Screenshots  

Include screenshots for each part in the `screenshots/` folder, such as:  
* Wazuh Agent running on Windows.  
* Wazuh Manager receiving alerts.  
* Shuffle playbook design.  
* VirusTotal enrichment results.  
* TheHive case creation.  
* Email/Slack notification.  

---

## Reflection & Lessons Learned  

* Learned how to integrate multiple SOC tools into one pipeline.  
* Hands-on practice with automation reduced manual SOC analyst effort.  
* Gained understanding of threat enrichment workflows using VirusTotal.  
* Realized the importance of structured case management in TheHive.  

---

## Future Enhancements  

* Add more enrichment sources (AbuseIPDB, OTX, etc.).  
* Automate response actions (disable user, isolate endpoint).  
* Integrate Slack or Teams for faster communication.  
* Expand detection rules in Wazuh for advanced threats.  

---
