# SOC Automation Project: Wazuh → Shuffle → TheHive

## Overview
This project demonstrates a full SOC automation workflow where a Windows 10 client with Wazuh Agent detects suspicious activity, sends events to Wazuh Manager, which forwards alerts to Shuffle SOAR. Shuffle enriches alerts using threat intelligence (e.g., VirusTotal) and forwards them to TheHive for case creation. SOC analysts are notified via email.

Technologies: Windows 10, Ubuntu Server, Wazuh, Shuffle SOAR, TheHive, VirusTotal.

## Folder Structure
- 01-Architecture-Diagram: Architecture diagrams
- 02-Windows-Client-Wazuh-Agent: Wazuh agent installation & configuration
- 03-Wazuh-Manager-Setup: Manager installation, alert rules
- 04-Shuffle-SOAR-Integration: SOAR automation & enrichment
- 05-TheHive-Integration: Case creation and alert forwarding
- 06-Alerts-and-Playbooks: Playbooks, alert examples, and screenshots
- screenshots: Screenshots of each step

## License
MIT License
