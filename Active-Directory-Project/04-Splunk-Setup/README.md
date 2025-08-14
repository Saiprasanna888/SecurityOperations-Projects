## **Step 1: Connect to Ubuntu Server**

1. Open a terminal or SSH client on your local machine.
2. Connect to your Ubuntu VM using SSH:

```bash
ssh username@UBUNTU_SERVER_IP
```

3. Update the package list:

```bash
sudo apt update && sudo apt upgrade -y
```

---

## **Step 2: Install Splunk**

### **Download Splunk**

1. Navigate to [Splunk Enterprise Downloads](https://www.splunk.com/en_us/download.html)
2. Copy the **Linux (deb)** download link.
3. Download Splunk to your server:

```bash
wget -O splunk.deb 'https://download.splunk.com/products/splunk/releases/X.X.X/linux/splunk-X.X.X-linux-2.6-amd64.deb'
```

*(Replace X.X.X with the latest version)*

### **Install Splunk**

```bash
sudo dpkg -i splunk.deb
```

### **Start Splunk**

```bash
sudo /opt/splunk/bin/splunk start --accept-license
```

* Set an **admin username and password** during first startup.

### **Enable Splunk to start at boot**

```bash
sudo /opt/splunk/bin/splunk enable boot-start
```

---

## **Step 3: Configure Splunk Web Access**

1. Splunk Web runs on port `8000`.
2. Open a browser and navigate to:

```
http://UBUNTU_SERVER_IP:8000
```

3. Log in with the admin credentials you set.

---

## **Step 4: Ingest Telemetry from Windows Endpoints**

### **Option 1: Using Universal Forwarder**

1. On Windows Server, download and install **Splunk Universal Forwarder**.
2. During installation, provide the **Splunk server IP** (Ubuntu VM) and receiving port (default `9997`).
3. Start the forwarder and verify logs are being sent.

### **Option 2: Using Syslog / Event Logs**

* Configure Splunk to collect **Windows Event Logs** via **WinRM or syslog forwarding**.
* Create a new **Data Input** in Splunk Web → **Add Data** → Select **Forwarded Data / Local Files / Windows Event Logs** → Follow prompts.

---

## **Step 5: Create Alert for Unauthorized Logins**

1. Go to **Search & Reporting App** in Splunk Web.
2. Run a search to detect failed or unauthorized logins:

```spl
index=wineventlog EventCode=4625 OR EventCode=4776
| stats count by Account_Name, src_ip
```

* `4625` = Failed login
* `4776` = NTLM authentication failure

3. Click **Save As → Alert**.

4. Configure alert settings:

   * **Trigger Condition:** Per Result
   * **Throttle:** Optional, to avoid repeated alerts
   * **Trigger Actions:**

     * Send Email
     * Run a Script (for automation later via Shuffle)

5. Name the alert: `"Unauthorized Login Alert"`

---

## **Step 6: Verify Alert**

1. Test by attempting a failed login with a test user account.
2. Check Splunk to see if the alert triggers.
3. Document results and take screenshots:

   * Splunk Web interface
   * Alert configuration
   * Sample event logs

---

## **Step 7: Document for GitHub**

* Create a `README.md` in `04-Splunk-Setup/` folder.
* Include:

  * Splunk installation commands
  * Screenshots of alerts and dashboards
  * Example search queries
  * Explanation of data sources and telemetry flow
