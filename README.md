

# RAM Dump Analysis using DumpIt & Volatility

This project demonstrates the complete workflow of capturing volatile memory (RAM) from a Windows system using DumpIt, and performing forensic analysis using the Volatility 3 Framework.



 🔍 Project Overview

* Acquired a live RAM dump using **DumpIt.exe**
* Transferred the dump to an analysis machine
* Analyzed the memory using **Volatility 3**
* Extracted key forensic artifacts:

  * Running processes
  * Active network connections
  * Executed commands (Command History)

This project highlights practical skills in memory acquisition, forensic analysis, and Volatility usage.
-

🛠️ Tools Used

| Tool                        | Purpose                             |
| --------------------------- | ----------------------------------- |
| **DumpIt**                  | RAM acquisition from Windows system |
| **Volatility 3**            | Memory forensic analysis            |
| **Windows Virtual Machine** | Source machine for acquisition      |
| **Host/Analysis Machine**   | Runs Volatility analysis            |

---

## 📥 **Step 1 — Acquire RAM Dump**

Used **DumpIt** inside the Windows VM to capture the RAM.

<img width="971" height="512" alt="dumpit_capture" src="https://github.com/user-attachments/assets/23ad814f-1b41-47f2-bc33-2a289a14020c" />


DumpIt generates a file similar to:

```
WIN10-YYYYMMDD-HHMMSS.raw
```

---

## 📤 **Step 2 — Move Dump to Analysis Machine**

The `.raw` memory file was moved to the **Volatility folder** on the host machine.

<img width="917" height="440" alt="volatility_folder" src="https://github.com/user-attachments/assets/912f5adb-cacf-44a2-9e4c-08c163d7fcfa" />


---



## 🔍 **Step 3 — Analyze RAM with Volatility 3**

## 📑 **Extracted Forensic Artifacts**

### ✔ 1. Running Processes
<img width="999" height="72" alt="volitility_cmd2" src="https://github.com/user-attachments/assets/2cd66365-e3b1-4965-8178-299ea6819559" />



Command:

```bash
vol.exe -f dump.raw windows.pslist > running_process.txt
```



---

### ✔ 2. Network Connections
<img width="999" height="72" alt="volitility_cmd2" src="https://github.com/user-attachments/assets/ad27d1b6-48c1-406b-97e8-2c4aa3f0e377" />


Command:

```bash
vol.exe -f dump.raw windows.netscan > network_connections.txt
```





---

### ✔ 3. Executed Commands (Command History)

<img width="1019" height="42" alt="Volitiity_cmd" src="https://github.com/user-attachments/assets/bcb6ead3-e282-47f3-8857-3f8cd1e793d9" />

Command:

```bash
vol.exe -f dump.raw windows.cmdscan > executed_cmd.txt
```





## 🎯 **Conclusion**

This project demonstrates:

* RAM dump acquisition
* Memory forensic investigation
* Volatility analysis skills
* Evidence extraction & documentation

Useful for:
**Cybersecurity internships, DFIR portfolios, and academic projects.**

---

## 📝 **Important Note**

This is a **dummy analysis performed on a clean test system**.
👉 **No malicious activity, suspicious processes, or abnormal network behavior was detected during the examination.**

