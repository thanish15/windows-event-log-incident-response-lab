# Incident Report

## Incident Overview

A simulated Windows environment was investigated using Splunk and Windows Event Logs. The investigation identified a sequence of suspicious authentication, process execution, PowerShell, scheduled-task, SMB, and LSASS activity.

## Key Findings

- Remote logon activity was observed from suspicious source IP addresses.
- PowerShell and other command-line processes were executed.
- Scheduled tasks under the `Updater` path were modified to execute PowerShell.
- ADMIN$ network share access was observed.
- A process named `diagtool.exe` accessed the LSASS process.

## Indicators

| Type | Indicator |
|---|---|
| IP Address | 10.20.30.40 |
| IP Address | 10.20.30.41 |
| File | C:\Users\Public\script.ps1 |
| File | C:\Tools\diagtool.exe |
| Scheduled Task | \Updater\SystemUpdate5 |
| Scheduled Task | \Updater\SystemUpdate6 |
| Network Share | ADMIN$ |

## Response Recommendations

1. Investigate the affected user accounts and source IP addresses.
2. Review the identified PowerShell commands and processes.
3. Verify whether the scheduled tasks are legitimate.
4. Review ADMIN$ access and related file activity.
5. Investigate LSASS access and check for possible credential theft.
6. Reset compromised credentials if unauthorized activity is confirmed.

## Conclusion

The investigation demonstrated how Windows security and Sysmon logs can be correlated in Splunk to reconstruct suspicious activity and identify artifacts requiring further investigation.
