🚩 Flag 3 – Sensitive Document Access

🧠 **Analysis**:

Using the query:
```kusto
DeviceFileEvents
| where DeviceName == "michaelvm"
| where Timestamp between (datetime(2025-06-15) .. datetime(2025-06-17))
| where FileName endswith ".docx" or FileName endswith ".pptx"
| where InitiatingProcessFileName in~ ("powershell.exe", "cmd.exe", "wscript.exe", "cscript.exe")
| project Timestamp, FileName, FolderPath, InitiatingProcessFileName
| order by Timestamp asc
```
out of 80 file base on name .locatipon and context the high suspicious file 
` 
QuarterlyCryptoHoldings.docx
📁 C:\Users\Mich34L_id\Documents\BoardMinutes\
✅ Contains both "BoardMinutes" and "CryptoHoldings"
🧠 Likely a summary of financials presented to the board — exactly what an attacker would want
'
 it’s in a BoardMinutes folder and directly references crypto holdings, aligning perfectly with the attacker’s motive.
 
 📎 **Supporting Evidence**
 
 ![](https://github.com/SruthinagaK/ThreatHunt-Lurker/blob/main/Flag3.png)


The link to go back to the  [scenario](https://github.com/SruthinagaK/ThreatHunt-Lurker)
