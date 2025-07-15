🚩 Flag 1 – Initial PowerShell Execution Detection
🎯 Objective:
Identify the first suspicious PowerShell script execution that may indicate the intruder's initial activity.

🧠 Analysis:
Using the following KQL query:
```kusto
DeviceProcessEvents
| where DeviceName == "michaelvm"
| where Timestamp between (datetime(2025-06-15) .. datetime(2025-06-17))
| where FileName == "powershell.exe"
| where ProcessCommandLine has ".ps1"
```
Discovered 225 PowerShell script executions on the device michaelvm during the suspicious timeframe.

