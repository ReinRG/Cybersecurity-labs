# Week 1 – Log Analysis 101 with Windows Event Viewer
# Completed - June 20, 2025

## Objective
Analyze Windows event logs to detect signs of unauthorized access, suspicious file changes, or brute-force login attempts.

---

## Tools Used
- Windows 10 Event Viewer
- Built-in Windows audit logging

---

## Steps Performed

1. Enabled audit policies in Local Security Policy.
2. Opened Event Viewer and filtered for:
   - Event ID 4624 (Successful login)
   - Event ID 4625 (Failed login)
   - Event ID 4663 (File access)
3. Simulated failed login attempts to generate Event ID 4625 logs.
4. Observed timestamps to understand the sequence of login events.

---

## Findings

| Time (UTC)   | Event ID | Description      | Notes                                          |
|--------------|----------|------------------|------------------------------------------------|
| 10:23:35 PM  | 4625     | Failed login      | Incorrect password entered by the user         |
| 10:23:39 PM  | 4624     | Successful login  | User logged in successfully after failure      |

---

## Screenshots

- `1-security-policy-logon.jpg`: Audit policy enabled for logon events
- `2-successful-login-sample-4624.jpg`: Sample of a successful login (Event ID 4624)
- `3-failed-login-sample-4625.jpg`: Sample of a failed login (Event ID 4625)
- `4-eventviewer-filter.jpg`: Filtered Security logs in Event Viewer
- `5-event-details-4625.jpg`: Login attempt analysis from Event Viewer

---

## Lessons Learned

- Learned how to enable Windows audit logging for login and file events.
- Gained hands-on experience using Event Viewer to analyze login activity.
- Understood how Event IDs correlate with user behavior and security incidents.
- Recognized the importance of screenshots and documentation in SOC reporting.

---

## Next Steps

- Learn how to set up centralized logging using Wazuh or a SIEM platform.
- Practice creating alert rules for failed login attempts and access to sensitive files.
