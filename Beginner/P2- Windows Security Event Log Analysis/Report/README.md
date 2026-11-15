# Windows Security Event Log Analysis
## Authentication Activity Investigation Report

**Project:** P2 — Windows Security Event Log Analysis  
**Log Source:** Windows Security Event Log (`.evtx`)  
**Host:** MSEDGEWIN10  
**Investigation Date:** 15 November 2026  
**Evidence Timestamp:** 09 September 2020, 18:48:23–18:48:27  
**Analyst:** Blue Team Intern

---

## 1. Executive Summary

This investigation examines Windows Security Event Log records from a sample EVTX file containing authentication activity associated with the local account `IEUser` and the Windows `SYSTEM` account.

A total of **four events** were identified: three successful logons (Event ID 4624) and one failed logon (Event ID 4625).

The investigation identified a failed authentication attempt for `IEUser`, followed approximately two seconds later by successful logon events for the same account. The records also show Chrome as the caller process associated with the IEUser authentication events.

The available evidence warrants review but does not establish malicious activity or account compromise.

## 2. Investigation Scope

The analysis focused on:

- Successful authentication events (Event ID 4624).
- Failed authentication events (Event ID 4625).
- Account names and logon types.
- Authentication failure status codes.
- Process information associated with logon activity.
- Event timestamps and record IDs.
- Relationships between logon sessions.

## 3. Tools and Data Sources

**Primary data source:**  
`CA_4624_4625_LogonType2_LogonProc_chrome.evtx`

**Analysis environment:** Windows PowerShell

**Command used:**

```powershell
$events = Get-WinEvent -Path ".\CA_4624_4625_LogonType2_LogonProc_chrome.evtx"
```

Events were examined using `Get-WinEvent`, filtering, sorting, and XML event metadata extraction.

## 4. Event Distribution

| Event ID | Description | Count |
|---|---|---:|
| 4624 | Successful logon | 3 |
| 4625 | Failed logon | 1 |
| **Total** | | **4** |

## 5. Detailed Findings

### Finding 1 — Failed Authentication

**Event ID:** 4625  
**Record ID:** 137222  
**Timestamp:** 09 September 2020, 18:48:23  
**Account:** IEUser  
**Logon Type:** 2 — Interactive  
**Caller Process:** `chrome.exe`

The event records an unsuccessful authentication request for the local account `IEUser`.

The failure information contains:

- Status: `0xC000006D`
- Substatus: `0xC000006A`
- Failure reason: Unknown user name or bad password.

The substatus indicates that the password was incorrect.

### Finding 2 — Successful SYSTEM Service Logon

**Event ID:** 4624  
**Record ID:** 137223  
**Timestamp:** 09 September 2020, 18:48:25  
**Account:** SYSTEM  
**Logon Type:** 5 — Service  
**Process:** `C:\Windows\System32\services.exe`

This event records a successful service logon under the Windows SYSTEM account.

The elevated token is expected for this privileged system context. The event is not, by itself, evidence of privilege escalation.

### Finding 3 — Successful IEUser Logon Sessions

**Event ID:** 4624  
**Record IDs:** 137224 and 137225  
**Timestamp:** 09 September 2020, 18:48:27  
**Account:** IEUser  
**Logon Type:** 2 — Interactive  
**Process:** `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`

Two successful logon events were recorded for `IEUser`.

Their logon session details show:

- One event with an elevated token.
- One event with a non-elevated token.
- Linked Logon IDs: `0x1CD8F6` and `0x1CD964`.
- Common subject Logon ID: `0x79E59`.

The linked session identifiers indicate that the two logon sessions are related. However, the available records do not establish the exact reason for their creation.

### Finding 4 — Authentication Process Context

The failed and successful IEUser authentication records reference:

`C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`

They also show the logon process as `Chrome` and authentication package as `Negotiate`.

The source network address is unavailable in these events. Therefore, the records do not provide evidence of a remote source IP address.

## 6. Event Timeline

| Timestamp | Record ID | Event ID | Activity |
|---|---:|---:|---|
| 18:48:23 | 137222 | 4625 | IEUser authentication failed |
| 18:48:25 | 137223 | 4624 | SYSTEM service logon |
| 18:48:27 | 137224 | 4624 | IEUser successful logon, elevated token |
| 18:48:27 | 137225 | 4624 | IEUser successful logon, non-elevated token |

All four events were recorded on `MSEDGEWIN10`.

## 7. Security Assessment

The investigation identified one failed authentication followed shortly by successful authentication events for the same account.

The shared subject Logon ID and Chrome process information provide useful correlation points for further investigation.

However, a single failed authentication followed by successful logons does not establish password spraying, brute-force activity, or unauthorized access.

The SYSTEM service logon is consistent with normal Windows service activity based on the available fields.

**Assessment:** Authentication activity observed; suspicious activity is not confirmed.

## 8. Recommended Defensive Actions

1. Review surrounding Security Event Logs to establish whether additional failed authentication attempts occurred.
2. Correlate the IEUser logon sessions with process creation and application activity.
3. Verify whether the Chrome-associated authentication activity was expected.
4. Monitor repeated Event ID 4625 occurrences involving the same account.
5. Investigate unexpected privileged logon sessions and validate their originating processes.
6. Preserve relevant event records for further investigation.

## 9. Investigation Limitations

- The supplied EVTX sample contains only four events.
- No source network address was available in the authentication records.
- The sample does not provide enough context to determine whether the failed authentication was malicious.
- No process creation, network connection, or endpoint telemetry was included to independently validate the activity.
- The investigation is limited to the supplied sample and does not represent a complete assessment of the host.

## 10. Conclusion

This investigation demonstrated the analysis of Windows Security Event Logs using PowerShell, including authentication event identification, account analysis, logon type interpretation, failure status examination, event correlation, and timeline reconstruction.

The key observation was a failed `IEUser` authentication followed by successful logon sessions within a short time window.

The evidence provides useful investigation leads but is insufficient to confirm an intrusion or compromise.

**Final Result:** Windows authentication activity successfully analysed and documented. No confirmed compromise established from the supplied evidence.
