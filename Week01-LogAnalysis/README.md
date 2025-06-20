# Week 1 – Log Analysis 101 with Windows Event Viewer

## Objective
Analyze Windows event logs to detect signs of unauthorized access, suspicious file changes, or brute-force login attempts.

---

## Tools Used
- Windows 10 Event Viewer
- Built-in Windows audit logging
- Optional: Wazuh Agent for log forwarding

---

## Steps Performed

1. Enabled audit policies in Local Security Policy.
2. Opened Event Viewer and filtered by:
   - Event ID 4624 (Successful login)
   - Event ID 4625 (Failed login)
   - Event ID 4663 (File access)
3. Identified suspicious login attempts from IP `xxx.xxx.xxx.xxx`.
4. Correlated timestamps with unusual activity.

---

## Findings

| Time (UTC) | Event ID | Description | Notes |
|------------|----------|-------------|-------|
| 12:30 PM   | 4625     | Failed login | 15 attempts in under 1 minute |
| 12:34 PM   | 4624     | Successful login | From new user account |
| 12:36 PM   | 4663     | File accessed | `confidential.docx` opened |

---

## Screenshots

*Include screenshots of your Event Viewer showing filtered logs, timestamps, or alerts.*

---

## Lessons Learned
- Windows Event Viewer can detect brute-force attempts through event ID patterns.
- Correlating login and file access events helps identify suspicious activity.
- Documentation is critical — timestamp everything!

---

## Next Steps
- Set up centralized logging with Wazuh or a SIEM.
- Create alert rules for rapid login attempts and access to sensitive files.
