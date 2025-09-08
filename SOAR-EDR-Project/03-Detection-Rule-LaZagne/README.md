# Detection Rule - LaZagne

This folder contains documentation for creating and testing a custom detection rule for **LaZagne** password recovery tool.

---

## **Objective**

- Detect the execution of LaZagne on endpoints.
- Generate alerts in LimaCharlie EDR.
- Trigger automated response in Tines SOAR.

---

## **Steps to Create Detection Rule**

1. Identify process name, file hash, or behavior patterns of LaZagne.
2. Log in to **LimaCharlie console**.
3. Navigate to **Detection Rules** → Create New Rule.
4. Configure conditions:
   - Process Name: `lazagne.exe`
   - File Hash (optional): `[hash value]`
   - Behavior: attempts to access password files, registry keys.
5. Set alert severity (e.g., High).
6. Assign rule to target endpoints.

---

## **Testing the Rule**

1. Run LaZagne on a test endpoint.
2. Confirm that LimaCharlie triggers an alert.
3. Verify that the alert is sent to **Tines SOAR**.
4. Document:
   - Endpoint affected
   - Alert timestamp
   - Screenshot of alert in LimaCharlie

---

## **Notes**

- Ensure the test endpoint is isolated and safe.
- Keep all detection logic and testing steps documented for SOC reference.
- Screenshots of alert flow can be saved in `screenshots/` folder.
