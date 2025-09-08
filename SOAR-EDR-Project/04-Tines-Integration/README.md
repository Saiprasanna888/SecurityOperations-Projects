# Tines Integration

This folder documents the **workflow creation** and **Slack integration steps** for automating SOC alerts using **Tines SOAR**.

---

## **Objective**
- Ingest alerts from **LimaCharlie EDR** into Tines.
- Automate response workflows.
- Notify SOC analysts via **Slack**.

---

## **Steps for Workflow Creation**

1. **Log in to Tines** platform.
2. **Create a new Story / Workflow**.
3. **Add an Incoming Webhook Action**:
   - URL: Provided by Tines.
   - Payload: JSON format from LimaCharlie alerts.
4. **Add a Filter / Condition Action**:
   - Check threat severity.
   - Check affected endpoint.
5. **Add Slack Action**:
   - Connect to Slack workspace.
   - Select SOC channel.
   - Map alert fields (hostname, user, threat type, timestamp).
6. **Optional Actions**:
   - Email notifications.
   - Case creation in TheHive.
   - Endpoint isolation commands.

---

## **Testing the Workflow**

1. Generate a test alert in **LimaCharlie** (e.g., LaZagne execution on a test endpoint).
2. Confirm alert is received in **Tines**.
3. Verify **Slack notification** is sent to the SOC channel.
4. Document test results:
   - Timestamp
   - Endpoint / user affected
   - Screenshots of Tines workflow and Slack alert

---

## **Notes**
- Ensure all API keys and credentials are stored securely.
- Keep workflows modular for easy updates.
- Screenshots can be stored in the `screenshots/` folder.

