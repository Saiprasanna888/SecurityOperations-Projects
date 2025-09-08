# Workflow Diagram
Contains diagrams showing the SOAR-EDR Project flow from LimaCharlie → Tines → Slack.


# SOAR EDR Playbook Workflow

This document provides a clear, step-by-step breakdown of the **SOAR EDR Playbook Workflow** using **LimaCharlie (EDR)** and **Tines (SOAR)** with Slack/Email notifications.

---

## 🔁 SOAR EDR Playbook Workflow - Step-by-Step

---

### 1️⃣ Detection of Threat
- **Source:** Endpoint becomes **infected**.
- **Action:** **LimaCharlie EDR** detects the threat on the infected endpoint.

---

### 2️⃣ Alert Generation
- **EDR (LimaCharlie)** sends a detection alert to the **SOAR platform (Tines)**.

---

### 3️⃣ Notification to Stakeholders
- **Tines** sends a message with threat details to:
  - **Slack**
  - **Email**

---

### 4️⃣ User Decision Prompt
- **Tines** prompts the user:
  > "Do you want to isolate the infected computer?"

---

## Branching Based on User Decision

---

### ✅ If the User Chooses "Yes" (Isolate the Machine)

#### 5️⃣ Isolation Action
- **Tines** communicates with **LimaCharlie** to **isolate the infected endpoint**.

#### 6️⃣ Isolation Confirmation
- Once isolated, a **Slack message** is sent:
  > "The computer `<computer>` has been isolated."

---

### ❌ If the User Chooses "No" (Do Not Isolate)

#### 7️⃣ Follow-Up Notification
- **Slack message** alerts the team:
  > "The computer `<computer>` was not isolated, please investigate."

---

## ✅ Outcome Summary
- 🔒 **Isolated:** Threat is contained and confirmed via Slack.
- 🚨 **Not isolated:** Team is alerted to investigate further.

---

## **Next Steps**
- Document the workflow in Tines with screenshots.
- Create test alerts in LimaCharlie to validate the workflow.
- Store all Slack/Email notification examples in `screenshots/`.

