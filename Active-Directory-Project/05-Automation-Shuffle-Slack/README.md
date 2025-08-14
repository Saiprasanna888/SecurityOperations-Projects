## **Step 1: Set Up Shuffle SOAR**

1. Log in to your **Shuffle instance** (can be hosted in the cloud or on-prem).
2. Ensure your **Splunk integration app** is installed in Shuffle:

   * Navigate to **Settings → Integrations**
   * Search for **Splunk** and **install / enable** it.
3. Ensure **Active Directory integration** is installed:

   * Install **AD app** in Shuffle
   * Provide credentials and domain controller info for connection

---

## **Step 2: Connect Splunk Alerts to Shuffle**

1. In Splunk, navigate to your alert: `"Unauthorized Login Alert"`
2. Under **Trigger Actions**, select **Webhook** (HTTP POST)
3. Copy the **Shuffle webhook URL** for the workflow you will create.
4. Configure the webhook in Splunk to send **alert payloads** (JSON format) to Shuffle.
5. Test webhook delivery by triggering a sample alert.

---

## **Step 3: Create Automation Playbook in Shuffle**

1. Navigate to **Workflows → Create New Workflow**
2. Name your workflow: `"Unauthorized Login Response"`
3. Add **Trigger**:

   * **Webhook trigger** → Listen for Splunk alert
4. Add **Actions**:

   * **Send Slack Notification**:

     * Channel: `#soc-alerts`
     * Message: `"Unauthorized login detected for user {{username}}. Disable account?"`
   * **Email SOC Analyst** (optional)
   * **Decision Node**: Wait for analyst approval → Yes / No

---

## **Step 4: Disable User in Active Directory**

1. If analyst selects **Yes**:

   * Add **AD app action → Disable User**
   * Use payload from Splunk webhook to identify `Account_Name`
2. Test workflow with a test user to ensure account is disabled automatically.

---

## **Step 5: Send Slack Notifications**

1. Ensure Slack integration is connected:

   * Slack app in Shuffle → Add workspace → Generate Bot token → Authorize
2. Configure workflow to send messages for:

   * Alert triggered
   * User disabled (success)
   * Errors (failure to disable)

---

## **Step 6: Verify End-to-End Automation**

1. Trigger a **failed login** on Windows endpoint.
2. Splunk alert triggers → sends webhook to Shuffle
3. Shuffle workflow executes → posts message to Slack
4. SOC analyst confirms → Shuffle disables the user in AD automatically
