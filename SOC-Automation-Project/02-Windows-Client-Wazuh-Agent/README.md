# Part 2: Windows Client & Wazuh Agent

## Description  
The Wazuh agent is installed on a Windows 10 client to monitor system events and forward alerts to the Wazuh Manager for centralized analysis.

## Tasks  

### 1. Download & Install Agent  
- Download the Windows Wazuh agent MSI package from the official site.  
- Run the installer and complete setup with default options.  

### 2. Configure Agent  
- Edit `ossec.conf` to point to your Wazuh Manager IP:  

  ```xml
  <server>
    <address>MANAGER_IP</address>
    <port>1514</port>
  </server>
  ```

- Save the configuration file.  
- Start the **Wazuh Agent** service from `services.msc` or using PowerShell:  

  ```powershell
  Start-Service wazuh-agent
  ```

### 3. Test Connectivity  
- Check agent status with PowerShell:  

  ```powershell
  wazuh-agent.exe status
  ```

- Verify logs are received in Wazuh Manager (`alerts.json`).  

### 4. Simulate Suspicious Activity  
- Generate failed login attempts on the Windows client.  
- Run a suspicious PowerShell command to trigger alerts.  
- Confirm that the alerts are forwarded to the Wazuh Manager.  
