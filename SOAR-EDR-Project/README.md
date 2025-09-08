# SOAR EDR Project 🚀

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Objectives](#objectives)  
3. [Environment Setup](#environment-setup)  
4. [Project Steps](#project-steps)  

   * [Step 1: Workflow Diagram](#step-1-workflow-diagram)  
   * [Step 2: LimaCharlie Setup](#step-2-limacharlie-setup)  
   * [Step 3: Detection Rule – LaZagne Activity](#step-3-detection-rule--lazagne-activity)  
   * [Step 4: Slack & Tines Integration](#step-4-slack--tines-integration)  
   * [Step 5: Playbook Automation](#step-5-playbook-automation)  
5. [Screenshots](#screenshots)  
6. [Reflection & Lessons Learned](#reflection--lessons-learned)  
7. [Future Enhancements](#future-enhancements)  
8. [Demo Video](#demo-video)  

---

## Project Overview

This project demonstrates an **EDR + SOAR integration** using **LimaCharlie** (endpoint detection & response) and **Tines** (automation workflows).  

* The **EDR tool (LimaCharlie)** detects suspicious activity on endpoints and sends alerts in real time.  
* The **SOAR platform (Tines)** receives these alerts and automatically runs a response playbook.  
* Actions such as **isolating the device**, **notifying SOC analysts via Slack**, and **logging the incident** happen instantly through automation.  

This integration helps **SOC teams respond faster and manage threats more efficiently**.  

---

## Objectives

* Install and configure **LimaCharlie** EDR.  
* Confirm that endpoint events are being generated and ingested.  
* Create a **custom detection rule** for LaZagne (password recovery tool).  
* Integrate **LimaCharlie → Tines → Slack**.  
* Automate a response playbook to isolate an endpoint and send analyst notifications.  

---

## Environment Setup

* **LimaCharlie** → Cloud-native EDR platform.  
* **Tines SOAR** → Workflow automation platform.  
* **Slack** → Team collaboration & notification tool.  

---

## Project Steps

### Step 1: Workflow Diagram

* Design a diagram showing the flow:  
  - Endpoint → LimaCharlie Detection → Tines Workflow → Isolation → Slack Notification.  
* Store in `01-Diagram/workflow.png`.  

### Step 2: LimaCharlie Setup

* Install and configure LimaCharlie agent on endpoint.  
* Validate telemetry is being collected.  
* Ensure alerts are visible in the LimaCharlie console.  
* Document setup in `02-LimaCharlie-Setup/README.md`.  

### Step 3: Detection Rule – LaZagne Activity

* Objective: Detect usage of **LaZagne** (password recovery tool).  
* Create a detection & response rule in LimaCharlie to trigger when LaZagne is executed.  
* Verify the alert is generated and forwarded.  
* Document in `03-Detection-Rule-LaZagne/README.md`.  

### Step 4: Slack & Tines Integration

* Setup Tines to ingest alerts from LimaCharlie (via webhook/API).  
* Configure Slack webhook in Tines for SOC notifications.  
* Test by running LaZagne on endpoint → verify Slack alert in SOC channel.  
* Document in `04-Tines-Integration/README.md`.  

### Step 5: Playbook Automation

* Build a playbook in Tines based on the workflow diagram.  
* Actions include:  
  - Detect suspicious process from LimaCharlie.  
  - Automatically isolate endpoint.  
  - Send alert to Slack SOC channel.  
  - Log incident for analyst review.  
* Document in `05-Playbook/README.md`.  

---

## Screenshots

Save screenshots in `screenshots/` folder, such as:  
* LimaCharlie dashboard showing detection.  
* Tines workflow editor.  
* Slack alert message.  
* Isolation confirmation.  

---

## Reflection & Lessons Learned

* Gained practical knowledge of **EDR–SOAR integration**.  
* Understood how **custom detection rules** improve security.  
* Realized the importance of **real-time Slack alerts** for analyst awareness.  
* Learned how to **automate endpoint isolation** using APIs.  

---

## Future Enhancements

* Add enrichment with VirusTotal or OTX.  
* Expand playbooks for malware, phishing, or lateral movement.  
* Integrate with TheHive for structured case management.  
* Automate remediation actions beyond isolation (disable user, block IP).  

---

## Demo Video

Add demo video here:  

[![Watch the demo](https://drive.google.com/uc?id=YOUR-VIDEO-ID)](https://drive.google.com/file/d/YOUR-VIDEO-ID/view?usp=drivesdk)  
