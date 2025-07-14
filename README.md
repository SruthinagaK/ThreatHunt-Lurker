# 🕵️‍♂️ Cyber Threat Hunt: Entry Point - "Lurker" Scenario

## 📌 Scenario Overview
A new device began acting strangely, echoing signs of a past compromise. By following the clues and analyzing each flag, you're piecing together the timeline of events to uncover the full scope of the threat and understand what really happened.

## 🎯 Investigation Objective

## 🚩 Flags

### FLAG 0: Starting Point
Identify the first machine to investigate based on:
- Activity within **June 15–17, 2025**
- **Executions from the Temp folder**
- Devices active for **2–3 days**

✅ **Answer**: `michaelvm`

🔗 Click the [flag 0: Starting Point](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag_0.md) to view full details.

### Flag 1 : Initial PowerShell Execution Detection

🧠 Summary:
The investigation focuses on identifying the first suspicious PowerShell script execution that may mark the intruder’s entry point. By detecting unusual PowerShell activity early in the timeline, we can begin to trace the attacker’s movements and understand how the compromise began.

🔍 Objective:
Find the earliest .ps1 script execution that deviates from normal behavior — especially based on unusual file paths or command-line patterns.

**The first suspicious PowerShell execution was:**

✅ **Answer**: 
`"powershell.exe" -ExecutionPolicy Bypass -File "C:\Users\Mich34L_id\CorporateSim\Investments\Crypto\wallet_gen_0.ps1" `

🔗 Click the [flag 1:  Initial PowerShell Execution Detection](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/flag_1.md)) to view full details.


