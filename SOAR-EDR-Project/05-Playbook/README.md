# Playbook Automation

This folder documents the **design and implementation of automated playbooks** in the SOAR workflow using **Tines SOAR**.

---

## **Objective**
- Automate response actions based on alerts from **LimaCharlie EDR**.
- Reduce SOC analyst workload and response time.
- Ensure consistent and auditable incident handling.

---

## **Steps for Playbook Design**

1. **Review Workflow Diagram**
   - Refer to the workflow created in the `01-Diagram` folder.
   - Identify detection triggers and response actions.

2. **Create New Playbook in Tines**
   - Name the playbook according to the alert type (e.g., LaZagne Detection Response).
   - Define the **trigger** (incoming alert from LimaCharlie).

3. **Add Actions**
   - **Endpoint Isolation:** Use LimaCharlie API to isolate affected machine.
   - **Slack Notification:** Send alert and action confirmation to SOC channel.
   - **Email Notification:** Optional, for management or compliance.
   - **Case Logging:** Optionally forward alert to TheHive for case creation.

4. **Set Conditions and Logic**
   - Decision branches for **Isolate / Do Not Isolate**.
   - Ensure correct sequencing and error handling.

5. **Test Playbook**
   - Generate test alert in LimaCharlie (e.g., LaZagne execution).
   - Verify each automated action executes as expected.
   - Capture screenshots of the playbook execution and notifications.

---

## **Key Points**
- Modular playbooks allow easy updates for new threats.
- Human-in-the-loop decisions ensure safe automation.
- All actions are logged for audit and reporting purposes.

---

## **Next Steps**
- Add screenshots of each playbook step in the `screenshots/` folder.
- Document additional playbooks for other detection rules.
- Maintain version history for each automated workflow.
