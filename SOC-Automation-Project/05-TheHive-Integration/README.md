# Part 5: TheHive Integration

## Description  
TheHive is a Security Incident Response Platform (SIRP) designed to help SOC teams investigate, track, and resolve security incidents efficiently.  
By integrating Shuffle with TheHive, enriched alerts can be automatically converted into cases, allowing analysts to focus on investigation and response rather than manual data entry.  

## Tasks  

### 1. Configure TheHive API in Shuffle  
- Connect Shuffle to TheHive using its REST API.  
- Authenticate with an API key or service account to enable secure communication.  
- Map alert fields (alert ID, severity, description, indicators) into TheHive’s case format.  

### 2. Auto-Create Cases for High-Severity Alerts  
- Define a workflow in Shuffle to automatically create cases in TheHive whenever a high-severity or critical alert is detected.  
- Ensure cases contain:  
  - Alert details from Wazuh.  
  - Enrichment results from VirusTotal or other TI sources.  
  - Severity level and tags for categorization.  

### 3. Assign Cases to SOC Analyst  
- Configure TheHive to automatically assign new cases to available SOC analysts based on predefined rules (e.g., round-robin, severity-based).  
- Analysts receive a structured case with all necessary details for investigation.  

### 4. Enable Notifications via Email  
- Integrate TheHive with email or messaging platforms (e.g., Slack, Microsoft Teams).  
- Notify SOC analysts when new cases are created or updated.  
- Ensure timely response to critical alerts.  

### 5. Benefits of TheHive Integration  
- **Centralized Case Management** → all incidents tracked in one platform.  
- **Faster Investigations** → analysts get enriched alerts with full context.  
- **Reduced Manual Work** → no need to manually create or assign cases.  
- **Better Collaboration** → team members can share findings and updates inside cases.  
