# 🕵️‍♂️ Cyber Threat Hunt: Entry Point - "Lurker" Scenario

## 📌 Scenario Overview
A new device began acting strangely, echoing signs of a past compromise. By following the clues and analyzing each flag, you're piecing together the timeline of events to uncover the full scope of the threat and understand what really happened.

## 🎯 Investigation Objective

## 🚩 Flags

### 🚩 FLAG 0: Starting Point
Identify the first machine to investigate based on:
- Activity within **June 15–17, 2025**
- **Executions from the Temp folder**
- Devices active for **2–3 days**

✅ **Answer**: `michaelvm`

🔗 Click the [flag 0: Starting Point](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag_0.md) to view full details.

### 🚩 Flag 1 : Initial PowerShell Execution Detection

🧠 Summary:
The investigation focuses on identifying the first suspicious PowerShell script execution that may mark the intruder’s entry point. By detecting unusual PowerShell activity early in the timeline, we can begin to trace the attacker’s movements and understand how the compromise began.

🔍 Objective:
Find the earliest .ps1 script execution that deviates from normal behavior — especially based on unusual file paths or command-line patterns.

**The first suspicious PowerShell execution was:**

✅ **Answer**: 
`"powershell.exe" -ExecutionPolicy Bypass -File "C:\Users\Mich34L_id\CorporateSim\Investments\Crypto\wallet_gen_0.ps1" `

🔗 Click the [flag 1:  Initial PowerShell Execution Detection](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/flag_1.md)) to view full details.
### 🚩 Flag 2 – Reconnaissance Script Hash
🎯 Objective:
Identify the binary or script used during the reconnaissance stage of the attack.

🔍 What to Hunt:
Look for signs of local reconnaissance activity, such as:

PowerShell scripts or executables that gather system, user, or network information.
Files with suspicious or uncommon hash values.
Scripts executed shortly after initial access.
💭 Thought:
Reconnaissance is often one of the first steps an attacker takes after gaining access. It helps them understand the environment before moving laterally or escalating privileges.

✅ Task:
Identify the hash value of the script or binary used for reconnaissance.

✅ **Answer**: 
`badf4752413cb0cbdc03fb95820ca167f0cdc63b597ccdb5ef43111180e088b0 `

🔗 Click the [Flag 2 – Reconnaissance Script Hash](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/flag_2.md)  to view full details.


### 🚩 Flag 3 – Sensitive Document Access

🎯 Objective:
Reveal the document accessed or staged by the attacker that indicates their motive or target.

🔍 What to Hunt:
Look for access to:

Meeting-related directories
Confidential financial or crypto documents
💭 Thought:
The attacker’s interest in financial data reveals their intent and motive. Following the trail of sensitive document access helps uncover what they were after — in this case, money.

✅ Answer:
The attacker accessed the following sensitive document:

`QuarterlyCryptoHoldings.docx `

This file likely contains confidential financial information and was a key target in the attacker’s operation.

🔗 Click here to view full details in [Flag 3]() to view full details.

### 🚩 Flag 4 – Last Manual Access to File


### 🚩 Flag 5 – LOLBin Usage: bitsadmin


### 🚩 Flag 6 – Suspicious Payload Deployment


### 🚩 Flag 7 – HTA Abuse via LOLBin


### 🚩 Flag 8 – ADS Execution Attempt


### 🚩 Flag 9 – Registry Persistence Confirmation


### 🚩 Flag 10 – Scheduled Task Execution


### 🚩 Flag 11 – Target of Lateral Movement


### 🚩 Flag 12 – Lateral Move Timestamp






