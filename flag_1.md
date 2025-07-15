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
On **June 16, 2025**, the device michaelvm executed **225 PowerShell commands**, many of which involved .ps1 scripts.Among these, four executions were marked as "High" elevation, indicating potentially privileged or sensitive activity.

The earliest of these was:
### powershell.exe -ExecutionPolicy Bypass -File "C:\Users\Mich34L_id\CorporateSim\Investments\Crypto\wallet_gen_0.ps1" 
## 📎 Supporting Evidence

📊 [**Excel Sheet**](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag_1.csv)
![](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag1_Hig_alert.png)
This command was executed at **3:38:07 PM**, and appears to be the initial suspicious activity in the timeline — likely the attacker’s entry point.

*These high-elevation executions suggest the attacker may have used PowerShell scripts to perform reconnaissance or prepare for further compromise.*


