# 🛡️ Ransomware Incident Response Plan

## 📘 Purpose
This document outlines the step-by-step response actions taken during the **DarkVault Ransomware Incident (July 2025)**.  
It follows the **NIST Incident Response Lifecycle**: Identification, Containment, Eradication, Recovery, and Lessons Learned.

---

## 🧩 1. Identification

### Objectives
- Detect and confirm the ransomware infection.
- Determine scope, systems affected, and potential entry point.

### Actions
- Reviewed EDR alerts indicating abnormal PowerShell executions.
- Confirmed `.darkvault` file extensions across HR and Finance systems.
- Verified presence of ransom notes and related registry entries.
- Collected initial indicators (file hash, C2 IP address, process commands).
- Activated the **Incident Response Team (IRT)** and escalated to SOC lead.

### Tools Used
- Splunk (log correlation and anomaly detection)  
- Endpoint Detection & Response (EDR) console  
- PowerShell event logs  
- Email gateway quarantine reports  

---

## 🧱 2. Containment

### Objectives
- Limit the spread of the ransomware and protect unaffected systems.

### Actions
- Immediately isolated infected systems (HR-PC-14, FIN-SRV-02) from the network.  
- Disabled shared drives and access to mapped network folders.  
- Blocked C2 IP `198.51.100.24` at the firewall.  
- Temporarily restricted PowerShell execution via Group Policy.  
- Initiated communication protocol — informing IT, HR, and Finance heads.

### Tools Used
- EDR isolation features  
- Windows Defender ATP  
- Firewall management console  
- Active Directory Group Policy  

---

## 🧹 3. Eradication

### Objectives
- Remove ransomware binaries, persistence mechanisms, and residual artifacts.

### Actions
- Conducted deep scans using Windows Defender and Malwarebytes.  
- Deleted malicious PowerShell scripts and related registry entries.  
- Removed scheduled tasks created by ransomware (`update.ps1`).  
- Validated system integrity post-cleanup through file hash comparisons.  
- Ensured affected systems remained isolated until confirmed clean.

### Tools Used
- Malwarebytes Anti-Malware  
- Microsoft Defender Offline  
- Registry Editor (manual inspection)  
- File Integrity Monitoring (FIM)  

---

## 🔄 4. Recovery

### Objectives
- Restore normal operations and validate the integrity of recovered systems.

### Actions
- Restored clean backups of affected systems from secure offsite storage.  
- Verified backup timestamps and hash integrity before reintroduction.  
- Conducted test logins and functionality checks before reconnecting systems.  
- Re-enabled shared drives once confirmed free of infection.  
- Monitored all restored systems for 72 hours post-recovery.

### Tools Used
- Veeam Backup & Replication  
- Windows Event Viewer  
- Splunk dashboard monitoring  

---

## 📢 5. Communication

### Objectives
- Maintain transparency, minimize panic, and ensure coordinated response.

### Actions
- Issued internal alerts via Teams and email to inform staff about ongoing containment.  
- Provided safe behavior reminders (no external email attachments, report suspicious activity).  
- Delivered daily situation updates to executives until incident closure.

### Communication Channels
- Microsoft Teams  
- Email (internal comms only)  
- Security incident hotline  

---

## 🧩 6. Lessons Learned

### Key Takeaways
- Need for stronger phishing simulations and user awareness programs.  
- Enforce macro execution restrictions by default.  
- Regular EDR tuning and alert refinement.  
- Validation of offsite backups and regular recovery drills.  
- Documented all findings in post-incident review for process improvement.

---

📌 *This playbook demonstrates a structured, proactive response to ransomware incidents, minimizing business disruption and ensuring swift recovery.*
