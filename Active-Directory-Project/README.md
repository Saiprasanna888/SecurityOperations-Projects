# Active Directory Project: SOC Hands-On Lab

## Table of Contents

1. [Project Overview](#project-overview)
2. [Objectives](#objectives)
3. [Environment Setup](#environment-setup)
4. [Project Steps](#project-steps)

   * [Part 1: Architecture Diagram](#part-1-architecture-diagram)
   * [Part 2: Cloud Setup](#part-2-cloud-setup)
   * [Part 3: Active Directory Setup](#part-3-active-directory-setup)
   * [Part 4: Splunk Configuration & Alerts](#part-4-splunk-configuration--alerts)
   * [Part 5: Shuffle & Slack Automation](#part-5-shuffle--slack-automation)
5. [Screenshots](#screenshots)
6. [Reflection & Lessons Learned](#reflection--lessons-learned)
7. [Future Enhancements](#future-enhancements)
8. [License](#license)

---

## Project Overview

This project demonstrates a full **Active Directory (AD) environment setup** integrated with **Splunk** for monitoring unauthorized logins and **Shuffle + Slack** for automation and response. It’s designed as a hands-on SOC (Security Operations Center) lab that can be showcased on your resume or portfolio.

Technologies used:

* Windows Server (Active Directory Domain Controller)
* Ubuntu Server (Splunk)
* Splunk Enterprise (Log monitoring & alerting)
* Shuffle SOAR (Automation & playbooks)
* Slack (Notifications)

---

## Objectives

* Design an AD environment diagram.
* Deploy virtual machines in the cloud and configure firewalls.
* Set up Active Directory domain, create users, and join computers to the domain.
* Collect telemetry from Windows endpoints and configure Splunk alerts for unauthorized logins.
* Automate responses using Shuffle and send notifications to Slack.

---

## Environment Setup

* **Cloud Platform**: Vultr (or Azure / AWS / On-Prem)
* **Windows Server**: Domain Controller
* **Ubuntu Server**: Splunk instance
* **Networking**: Basic firewall rules to allow RDP, SMB, and Splunk communication

> *Note*: For local deployment, additional configurations may be required (outside scope).

---

## Project Steps

### Part 1: Architecture Diagram

* Create a clear diagram of the environment showing:

  * AD Domain Controller
  * Client machines
  * Splunk server
  * Shuffle and Slack integration
* Diagram stored in: `01-Diagram/AD-Environment-Diagram.png`

### Part 2: Cloud Setup

* Spin up virtual machines (Windows & Ubuntu) in your cloud provider.
* Configure firewall to allow required ports (RDP, SMB, Splunk).
* Document VM specs and network configuration.
* Reference: `02-Cloud-Setup/README.md`

### Part 3: Active Directory Setup

* Install Active Directory on Windows Server and promote it to a Domain Controller.
* Join client machine(s) to the domain.
* Create multiple user accounts.
* Verify logins and document any test users.
* Reference: `03-AD-Setup/README.md`

### Part 4: Splunk Configuration & Alerts

* Install Splunk on Ubuntu Server.
* Configure log ingestion from Windows endpoints.
* Create alert to detect **unauthorized successful logins**.
* Document Splunk alert configuration and sample logs.
* Reference: `04-Splunk-Setup/README.md`

### Part 5: Shuffle & Slack Automation

* Integrate Shuffle SOAR with Slack.
* Create an automation playbook:

  * Detect unauthorized login alert from Splunk
  * Send notification to Slack & email SOC analyst
  * If analyst confirms, disable the user in AD automatically
* Reference: `05-Automation-Shuffle-Slack/README.md`

---
## How to Use This Repo

1. Clone the repository:

```bash
git clone https://github.com/USERNAME/SecurityOperations-Projects.git
cd SecurityOperations-Projects
```

2. Navigate to the project folder you want to explore:

```bash
cd Active-Directory-Project
```

3. Follow the `README.md` in each project folder for **step-by-step instructions, screenshots, and configurations**.
4. Add screenshots, logs, or modifications as you practice.
   
---
## Screenshots

Include screenshots for each step in `screenshots/` folder, e.g.:

* VM creation
* AD user creation
* Splunk alerts
* Slack notification & automation

---

## Reflection & Lessons Learned

* Importance of centralized logging for security monitoring
* Hands-on experience with AD, Splunk, and SOAR integration
* Automation reduces response time for critical alerts

---

## Future Enhancements

* Add more types of alerts (failed logins, privilege escalations)
* Extend automation to disable multiple suspicious users
* Integrate with email/SMS notifications

---

## License

[MIT License](LICENSE)

---
