🚩 Flag 2 – Reconnaissance Script Hash
🎯 Objective:
Identify the PowerShell script used during the reconnaissance phase of the attack and its associated SHA256 hash. 

🧠 Analysis:

Using the query:
```kusto
DeviceProcessEvents
| where DeviceName == "michaelvm"
| where Timestamp between (datetime(2025-06-15 14:45:00) .. datetime(2025-06-16 15:38:00))
| where ProcessCommandLine has_any ("systeminfo", "ipconfig", "whoami", "Get-Process", "Get-Service", "netstat", "Get-NetTCPConnection", ".ps1")
| project Timestamp, ProcessCommandLine, FileName, FolderPath, SHA256
```
🧠 Why This Time Range Makes Sense:

Start Time (June 15, 2025 – 14:45)

This likely marks the beginning of suspicious activity or the earliest known signs of compromise. It helps you capture any initial reconnaissance or setup actions that may have occurred before the main execution.

End Time (June 16, 2025 – 15:38)

This aligns with the timestamp of the first confirmed malicious PowerShell execution:

`**wallet_gen_0.ps1 executed at 3:38:07 PM on June 16**`

So capturing everything leading up to and including that critical moment.

## Recon Timing
Reconnaissance typically happens right after initial access but before lateral movement or payload execution. This window is ideal for identifying commands like systeminfo, ipconfig, whoami, etc., which attackers use to understand the environment.

Withtin the time range specified  in the query  theSHA256 Hash value : `badf4752413cb0cbdc03fb95820ca167f0cdc63b597ccdb5ef43111180e088b0`appears 73 times .
- This hash is associated with cmd.exe launching PowerShell scripts using bypassed execution policies. These commands are not typical of standard user or system behavior and often indicate scripted or automated attack activity.
- The hash appears 73 times in the dataset, showing repeated use across multiple stages of the attack — including downloading and executing scripts like:
  - pwncrypt.ps1
  - eicar.ps1
  - portscan.ps1
  - exfiltratedata.ps1
 This repetition suggests the hash is tied to a core component of the attack infrastructure.
- The first appearance of this hash was at 2:13:29 AM on June 16, 2025, shortly before the initial malicious PowerShell script (wallet_gen_0.ps1) was executed. This timing places it in the early phase of the attack, likely during reconnaissance or payload staging.
- The hash is tied to cmd.exe commands that:
  - Use Invoke-WebRequest to download scripts.
  - Use -ExecutionPolicy Bypass to avoid security restrictions.    
  - Target C:\programdata\ — a common location for attacker-staged files.
  These are all red flags in endpoint behavior analysis.

📎 Supporting Evidence

🖼️ **Screenshot**:To support the evidence  of the SHA256 Recon valude the screen shot of the sha vlaue present 73 time after  eexcuting the query.
![](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag2.png)

📊 [**Excel Sheet**](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag_2.csv) 
