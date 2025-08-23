# 3: Wazuh Manager on Ubuntu Server

## Description  
Install Wazuh Manager on Ubuntu Server and configure alert rules for suspicious activity.

## Tasks  

### 1. Install Wazuh Manager  
- Install the Wazuh Manager package on the Ubuntu server.  
- Ensure the service is running properly after installation.  

### 2. Configure Agent Registration  
- Enable agent registration in the Wazuh Manager configuration.  
- Allow Windows and other clients to connect securely.  

### 3. Define Rules for Suspicious Events  
- Create custom rules for detecting failed logins, suspicious commands, or abnormal behavior.  
- Apply these rules in the local rules configuration.  

### 4. Forward Alerts to Shuffle SOAR  
- Configure Wazuh Manager to forward alerts to Shuffle SOAR using HTTP output integration.  
- Validate that alerts from Wazuh are received and processed in Shuffle SOAR.  

