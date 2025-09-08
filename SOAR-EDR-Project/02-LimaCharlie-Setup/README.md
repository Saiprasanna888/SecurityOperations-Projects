# LimaCharlie Setup Guide

This guide explains how to set up a LimaCharlie EDR lab environment using Windows and Ubuntu VMs.

---

## **Step 1: Choose Your Cloud Platform**

You can use **Vultr, AWS, Azure, or any other provider**. For this guide, we’ll use **Vultr** as an example.

---

## **Step 2: Spin Up Virtual Machines**

### **Windows VM (for endpoint/AD testing)**

1. Log in to your cloud provider dashboard.
2. Click **Deploy New Server** → choose **Windows 10 / Windows Server 2022**.
3. Select server location closest to you.
4. Choose instance size:
   * Recommended: 2 vCPU, 4GB RAM minimum.
5. Add additional storage if needed (50–100 GB recommended).
6. Set a strong **administrator password**.
7. Click **Deploy / Launch Server**.
8. Note the **public IP** and login credentials.


---

## **Step 3: Configure Firewall Rules**

### **Required Ports**

| Purpose                        | Port | Protocol |
| ------------------------------ | ---- | -------- |
| RDP (Windows access)           | 3389 | TCP      |

### **Steps**

1. Go to the cloud dashboard → **Firewall / Security Groups**.
2. Create a new firewall rule set.
3. Add rules for **RDP
4. Attach the firewall to both VMs.
5. Test connectivity:
   * RDP to Windows VM

---

## **Step 4: Install LimaCharlie Agent on Windows**

1. Download the LimaCharlie agent from the official portal.
2. Run the installer as administrator.
3. Configure it to connect to your LimaCharlie account using API keys.
4. Verify the agent is online in the LimaCharlie console.
5. Optional: Enable telemetry for process, network, and file monitoring.

---

## **Step 5: Verify Setup**

1. Ensure Windows VM is reporting to LimaCharlie.
2. Run a test alert (e.g., create a suspicious file or process).
3. Verify the alert appears in LimaCharlie console.
4. Document the setup:
   * VM specs
   * IP addresses
   * Installed software
   * Screenshots of console and agent status

> Keep a `screenshots/` folder in this directory for all relevant images.

