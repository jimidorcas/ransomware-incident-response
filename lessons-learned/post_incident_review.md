# 🔁 Post-Incident Review – DarkVault Ransomware Case

## 🗓️ Incident Summary
On **16 July 2025**, a ransomware variant known as **DarkVault** was identified within the HR and Finance departments.  
The attack originated from a phishing email containing a macro-enabled Excel file (`Payroll_Update_July2025.xlsm`).  
Prompt detection, containment, and restoration actions successfully prevented data loss and minimized business disruption.  

---

## 🧭 Root Cause Analysis
| Category | Details |
|-----------|----------|
| **Primary Cause** | Human error – a user enabled macros on a malicious attachment. |
| **Technical Cause** | Execution of embedded PowerShell script that downloaded and executed ransomware payload. |
| **Security Gaps Identified** | - Inadequate macro restriction policies.<br>- Insufficient email filtering and attachment sandboxing.<br>- Inconsistent phishing awareness across departments. |

---

## 📊 Response Evaluation
| Phase | What Worked Well | Areas for Improvement |
|-------|------------------|------------------------|
| **Identification** | EDR alerted SOC within minutes; prompt escalation to IR team. | Improve real-time notification workflows between SOC and IT. |
| **Containment** | Network segmentation and isolation limited lateral spread. | Enhance automated containment triggers for faster response. |
| **Eradication** | Malware removal was thorough; all IOCs documented. | Introduce automated IOC blocking in SIEM. |
| **Recovery** | Backups restored successfully; zero ransom paid. | Conduct regular recovery drills to validate RTO objectives. |
| **Communication** | Clear internal updates reduced panic; executives kept informed. | Introduce predefined message templates for faster dissemination. |

---

## 🧠 Key Lessons Learned
1. **User Awareness is the First Line of Defense**  
   Regular phishing simulations and awareness campaigns must be sustained across all departments.  
2. **Restrict Macros and Scripts by Default**  
   Enforce Group Policy to disable macro execution and script downloads unless explicitly approved.  
3. **Automate and Integrate Detection Workflows**  
   Implement SIEM-EDR integration for faster alerting and automatic isolation of high-risk endpoints.  
4. **Backup Validation is Critical**  
   Continue quarterly backup verification tests to ensure rapid recovery capability.  
5. **Centralized Incident Documentation**  
   Standardize post-incident reporting templates to streamline future investigations.  

---

## 🚀 Preventive Measures Implemented
- Macro execution now disabled for all users except administrators.  
- Enhanced email filtering with attachment sandboxing enabled.  
- Mandatory phishing awareness training scheduled quarterly.  
- Updated incident response runbooks added to SOC documentation.  
- Periodic ransomware simulation exercises included in 2025 security roadmap.  

---

## ✅ Conclusion
The **DarkVault ransomware incident** was contained and resolved without data loss or ransom payment.  
The event reinforced the importance of early detection, user vigilance, and layered defenses.  
Lessons learned have been integrated into updated policies and training initiatives to improve overall cyber resilience.

📌 *Report prepared by:* **Information Security & Incident Response Team**  
📅 *Date:* 22 July 2025
