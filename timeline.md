# Incident Timeline

The following timeline summarizes the main suspicious activity observed in the Windows event logs.

| Stage | Activity | Evidence |
|---|---|---|
| Initial Access | Remote logon activity | Windows Event ID 4624 |
| Execution | Suspicious process creation | Windows Event ID 4688 |
| Execution | Suspicious PowerShell commands | Event ID 4104 |
| Persistence | Scheduled task modified to run PowerShell | Event ID 4702 |
| Lateral Movement | ADMIN$ network share access | Event IDs 5140/5145 |
| Credential Access | LSASS process access | Sysmon Event ID 10 |

## Summary

The investigation showed a sequence of suspicious authentication, execution, persistence, lateral-movement-related, and credential-access activity.

The events were reviewed chronologically in Splunk to understand the overall incident pattern.
