## Azure Sentinel SOC Lab: Windows Security Monitoring & Failed Logon Detection

### Overview

This project uses Microsoft Azure and Microsoft Sentinel to monitor Windows security events and detect repeated failed logon attempts. I built it as a hands-on cloud security lab to practise security monitoring, threat detection, and incident investigation.

### Objectives

- Collect Windows Security events using Azure Monitor Agent.
- Analyse failed logon events using Kusto Query Language (KQL).
- Configure an analytics rule to detect repeated failed logon attempts.
- Generate and investigate a security incident in Microsoft Sentinel.
- Extract source IP addresses and target usernames from event data.

### Tools and Technologies

- Microsoft Azure
- Microsoft Sentinel
- Log Analytics workspace
- Azure Monitor Agent
- Windows Server
- Kusto Query Language (KQL)

### Detection Logic

The detection query analyses Windows Event ID `4625`, which represents a failed logon attempt. It extracts the source IP address and target username from the event data, groups events into five-minute intervals, and identifies groups with three or more failed attempts.

The analytics rule is configured to run every five minutes and examine the previous ten minutes of data.

See [`detection.kql`](detection.kql) for the query.

### Implementation

1. Configured a Windows Server virtual machine in Azure.
2. Connected Windows Security event collection to a Log Analytics workspace using Azure Monitor Agent.
3. Queried and analysed failed logon events in Log Analytics.
4. Created a Microsoft Sentinel analytics rule to identify repeated failed logon attempts.
5. Configured IP address and account entity mappings.
6. Reviewed the resulting security incident and its available entities.

### Evidence

### 1. Detection Query

![KQL detection query](detection-query.png)

### 2. Log Results

![Failed logon log results](log-results.png)
### 3. Incident Evidence

![Microsoft Sentinel incident details](incident-evidence.png)

### Skills Demonstrated

- Security event analysis
- KQL query development
- SIEM monitoring and alert configuration
- Failed logon detection
- Entity mapping
- Security incident investigation
- Cloud security fundamentals

### Disclaimer

This project was conducted in a controlled lab environment for learning and portfolio purposes. The detection logic is intended for demonstration and may require adjustment for production environments.
