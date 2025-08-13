## **Step 1: Choose Your Cloud Platform**

You can use **Vultr, AWS, Azure, or any other provider**. For this guide, we’ll use **Vultr** as an example.

---

## **Step 2: Spin Up Virtual Machines**

### **Windows Server VM**

1. Log in to your cloud provider dashboard.
2. Click **Deploy New Server** → choose **Windows Server 2022**.
3. Select server location closest to you (for low latency).
4. Choose instance size (RAM, CPU) based on lab needs:

   * Recommended: 2 vCPU, 4GB RAM minimum for AD lab.
5. Add additional storage if needed (50–100 GB recommended).
6. Set a strong **administrator password**.
7. Click **Deploy / Launch Server**.
8. Note the **public IP** and **login credentials**.

### **Ubuntu Server VM**

1. Deploy another server, choose **Ubuntu 22.04 LTS**.
2. Select similar or slightly lower specs (2 vCPU, 2GB–4GB RAM).
3. Set authentication: either password or SSH key.
4. Deploy the server and note its **public IP** and **credentials**.

---

## **Step 3: Configure Firewall Rules**

### **Basic Required Ports**

| Purpose                        | Port | Protocol |
| ------------------------------ | ---- | -------- |
| RDP (Windows access)           | 3389 | TCP      |
| SSH (Ubuntu access)            | 22   | TCP      |
| SMB (Active Directory traffic) | 445  | TCP      |
| Splunk Web                     | 8000 | TCP      |
| Splunk Management              | 8089 | TCP      |
| Any other app or service ports | —    | —        |

### **Steps**

1. In cloud dashboard, navigate to **Firewall / Security Groups**.
2. Create a new firewall rule set.
3. Add rules for **RDP**, **SSH**, **SMB**, **Splunk**, etc., as shown above.
4. Attach the firewall to your Windows and Ubuntu VMs.
5. Test connectivity:

   * From your local PC, try RDP to Windows VM.
   * Try SSH to Ubuntu VM.

---

## **Step 4: Document VM Specs**

Keep a document (e.g., `VM-Specs.md`) in your project folder with details:

**Example:**

| VM Name       | OS Version          | CPU | RAM  | Storage | IP Address   | Purpose           |
| ------------- | ------------------- | --- | ---- | ------- | ------------ | ----------------- |
| AD-Server     | Windows Server 2022 | 2   | 4 GB | 50 GB   | 192.168.1.10 | Domain Controller |
| Splunk-Server | Ubuntu 22.04 LTS    | 2   | 2 GB | 50 GB   | 192.168.1.11 | SIEM / Log Server |

> Include additional notes: login credentials (securely), installed software, network configuration.

---

## **Step 5: Verify Setup**

1. RDP to Windows VM → ensure you can log in.
2. SSH to Ubuntu VM → ensure you can connect.
3. Check firewall: ensure only required ports are accessible.
4. Take screenshots of cloud dashboard, firewall rules, and login screens.
