# 💥 Ransomware Incident Scenario – Case Study

## 🧭 Overview
On **Tuesday, 16 July 2025**, at approximately **09:42 AM**, the IT department detected unusual file encryption activity across shared drives belonging to the **Finance and HR departments**.  
Further investigation confirmed a **ransomware infection** that spread through a phishing email containing a malicious Excel attachment.

---

## 🧩 Attack Summary
| Category | Details |
|-----------|----------|
| **Incident Type** | Ransomware (Data Encryption & Extortion) |
| **Initial Vector** | Phishing Email with malicious macro-enabled Excel file |
| **Ransomware Family** | “DarkVault” (variant of LockBit) |
| **Affected Departments** | Finance, HR, Shared Network Drives |
| **Impact** | 42 systems encrypted; access to payroll and employee records disrupted |
| **Ransom Note** | “Your files have been encrypted. Pay 3 BTC within 72 hours or all data will be leaked.” |

---

## 🕒 Timeline of Events

| Time | Event |
|------|-------|
| **09:42 AM** | User in HR reports “Excel file not opening” after enabling macros. |
| **09:47 AM** | EDR alert triggered for suspicious PowerShell execution on HR-PC-14. |
| **09:55 AM** | Files on HR and Finance network shares begin renaming with `.darkvault` extension. |
| **10:05 AM** | Multiple endpoints disconnected automatically by the EDR quarantine policy. |
| **10:15 AM** | Security Operations team confirms ransomware infection. |
| **10:30 AM** | Containment initiated – shared drives isolated from the network. |
| **11:00 AM** | Incident Response plan activated. SOC and IT leads notified. |
| **12:15 PM** | Ransom note discovered on compromised systems. |
| **01:30 PM** | Forensic imaging and log collection initiated. |
| **02:00 PM** | Backup validation and restoration planning started. |
| **04:45 PM** | Partial service restored from clean backups. No ransom paid. |

---

## 🧠 Indicators of Compromise (IOCs)
| Category | Indicator | Description |
|-----------|------------|-------------|
| File Hash | `a8c93f0b2d8f35a6e9b9d56f0a1f7cdd` | Malicious Excel file attachment |
| File Name | `Payroll_Update_July2025.xlsm` | Phishing attachment |
| Process | `powershell.exe -exec bypass -File update.ps1` | Malicious PowerShell command |
| Registry Key | `HKCU\Software\Microsoft\Windows\CurrentVersion\Run\darkvault` | Persistence mechanism |
| Network | `198.51.100.24:443` | C2 communication endpoint |
| Extension | `.darkvault` | Encrypted file extension |

---

## ⚙️ Root Cause
The initial infection occurred when an HR employee **enabled macros** in a phishing email attachment.  
The Excel file executed an embedded PowerShell script that downloaded and executed the **DarkVault ransomware payload** from a remote command-and-control server.

---

## 📈 Impact Assessment
- 42 systems affected, 6 servers isolated, 2 days of partial downtime.  
- Financial data and HR records were encrypted but **successfully restored** from verified backups.  
- No confirmed data exfiltration.  
- Ransom not paid.  

---

## 🧰 Key Takeaways
- **User awareness** remains a critical weak point — phishing training reinforcement required.  
- **Macro execution policies** to be restricted via Group Policy.  
- **Network segmentation** proved effective in limiting lateral movement.  
- **Validated backups** were crucial for full recovery without paying ransom.

---

📌 *This case demonstrates the importance of layered defense, incident preparedness, and timely containment in mitigating ransomware impact.*
