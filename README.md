# SecurityOperations-Projects: Hands-On Security Operations Center Labs

This repository contains **hands-on Security Operations Center (SOC) projects** designed for aspiring SOC Analysts and cybersecurity enthusiasts. Each project demonstrates practical skills in monitoring, threat detection, incident response, automation, and integration of enterprise-grade tools. These projects are intended for **portfolio building**, resume enhancement, and practical skill development in real-world SOC environments.

## Objectives

* Gain **hands-on SOC experience** with real-world tools and scenarios.  
* Set up and monitor **Active Directory and endpoint environments**.  
* Implement **log collection, threat detection, and automated incident response** using SIEM and SOAR platforms.  
* Build and document **practical projects** to showcase skills for cybersecurity roles.  


## Technologies & Tools

* **Operating Systems:** Windows Server (AD, RDP, SMB), Ubuntu Server (Syslog, Services)  
* **Monitoring & SIEM:** Splunk Enterprise, Wazuh, ELK Stack (Elasticsearch, Logstash, Kibana)  
* **Automation & SOAR:** Shuffle SOAR, Tines, Cortex Responders (with TheHive)  
* **Collaboration & Notification:** Slack, Email (SMTP/Gmail/Outlook APIs)
* **Cloud Platforms:** Vultr, Azure (Sentinel, Cloud AD), AWS (EC2, Security Hub), GCP (Cloud Logging)  
* **Others:** RDP, SMB, Firewalls (pfSense, iptables, UFW), Active Directory, VirusTotal, AbuseIPDB

## Projects Overview

| Project Name             | Description                                                         | Status      | Folder                      |
| ------------------------ | ------------------------------------------------------------------- | ----------- | --------------------------- |
| **Active Directory 1.0** | Full AD environment setup with Splunk alerting & Shuffle automation | ✅ Completed | `Active-Directory-Project/` |
| **Wazuh-SOAR-TheHive Pipeline** | Wazuh + Shuffle SOAR + TheHive integration for automated SOC workflows      | ✅ Completed | `Wazuh-SOAR-TheHive/`       |
| **SOAR-EDR Project**            | LimaCharlie EDR + Tines SOAR + Slack integration for automated incident response | ✅ Completed | `SOAR-EDR-Project/` |

> Each project includes step-by-step instructions, screenshots, configuration files, and sample logs.

## Folder Structure

```
SecurityOperations-Projects/
│
├── Active-Directory-Project/
│   ├── 01-Diagram/
│   ├── 02-Cloud-Setup/
│   ├── 03-AD-Setup/
│   ├── 04-Splunk-Setup/
│   ├── 05-Automation-Shuffle-Slack/
│   ├── screenshots/
│   └── README.md
│
├── Wazuh-SOAR-TheHive/
│ ├── 01-Diagram/
│ ├── 02-Wazuh-Setup/
│ ├── 03-Shuffle-Setup/
│ ├── 04-TheHive-Integration/
│ ├── 05-Email-Alerts/
│ ├── screenshots/
│ └── README.md
|
├── SOAR-EDR-Project/
├── 01-Diagram/
├── 02-Limacharlie-Setup/
├── 03-LaZagne-Detection/
├── 04-Tines-Integration/
├── 05-Slack-Alerts/
├── screenshots/
└── README.md
│
└── README.md   # Main repo overview
```
## Contribution Guidelines

* Follow the existing folder structure for new projects.
* Include detailed `README.md` for each project.
* Add screenshots, sample logs, and configuration files.
* Use clear commit messages for every change.

## Future Enhancements

* Add more SOC projects (e.g., Threat Hunting, Malware Analysis, Cloud Security, Incident Response).
* Include demo videos and GIFs of key steps.
* Integrate CI/CD for automation of lab deployments.
* Expand alert and playbook examples for advanced scenarios.

## License

This repository is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

