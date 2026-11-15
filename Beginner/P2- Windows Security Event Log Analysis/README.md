# P2 — Windows Security Event Log Analysis

### Investigating Authentication Activity, Suspicious Behaviour & Windows Security Events


## Overview

Windows systems continuously generate security events that provide valuable insight into authentication activity, account usage, privilege assignments and process execution.

This project focuses on analysing Windows Security Event Logs from a defensive security perspective. The objective is to investigate potentially suspicious activity, identify authentication patterns, interpret important event identifiers and develop practical detection logic using PowerShell.

Rather than simply collecting event records, this investigation aims to understand what happened, identify indicators that deserve further attention and document findings in a structured SOC-style format.

## Investigation Objectives

- Examine Windows Security Event Logs and understand their structure.
- Identify repeated failed authentication attempts.
- Investigate successful and unsuccessful account logons.
- Analyse privileged account activity.
- Examine process creation events for potentially suspicious execution.
- Identify unusual authentication patterns and security indicators.
- Develop PowerShell-based log filtering and detection techniques.
- Document findings and provide appropriate defensive recommendations.

## Key Windows Event IDs

The investigation will focus on the following Windows Security Event IDs:

| Event ID | Description | Investigation Purpose |
|---|---|---|
| 4624 | Successful logon | Identify successful authentication activity |
| 4625 | Failed logon | Investigate unsuccessful authentication attempts |
| 4672 | Special privileges assigned to new logon | Examine privileged account activity |
| 4688 | Process creation | Investigate process execution activity |

These events provide a foundation for understanding Windows authentication and endpoint activity.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Windows Event Viewer | Inspect and review Windows event records |
| PowerShell | Filter, extract and analyse event data |
| Windows Security Logs | Primary investigation evidence |
| MITRE ATT&CK | Map observed behaviour to adversary techniques |
| GitHub | Maintain investigation documentation and evidence |

## Investigation Methodology

The project follows a structured investigation workflow:

1. **Log Collection** — Retrieve relevant Windows Security Event Logs.
2. **Event Filtering** — Extract records using event identifiers and relevant fields.
3. **Authentication Analysis** — Examine successful and failed logon activity.
4. **Behavioural Investigation** — Review suspicious account and process activity.
5. **Detection Development** — Create PowerShell queries and detection logic.
6. **Evidence Documentation** — Record observations, timestamps and relevant event details.
7. **Security Recommendations** — Suggest appropriate monitoring and defensive measures.


*The structure will be populated as the investigation progresses.*

## Expected Deliverables

- Structured Windows Security Event Log analysis.
- PowerShell commands and detection queries.
- Documented suspicious authentication patterns.
- A findings register containing evidence and investigation status.
- A professional security investigation report.
- Screenshots demonstrating the analysis process.

## Security Relevance

Windows Security Event Logs are an important source of endpoint telemetry for Security Operations Centre (SOC) teams.

Monitoring authentication failures, successful logons, privileged access and process creation can help analysts identify suspicious behaviour and investigate potential security incidents.

This project introduces practical techniques associated with:

- Account Discovery and Authentication Monitoring.
- Brute Force Detection.
- Privileged Account Monitoring.
- Process Execution Analysis.
- Security Event Correlation.

Relevant MITRE ATT&CK techniques will be mapped only where supported by the investigation evidence.

## References & Knowledge Base

- [Microsoft Learn — Windows Security Auditing](https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/basic-audit-logon-events)
- [Microsoft Learn — Event 4624](https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4624)
- [Microsoft Learn — Event 4625](https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4625)
- [Microsoft Learn — Event 4672](https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4672)
- [Microsoft Learn — Event 4688](https://learn.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4688)
- [MITRE ATT&CK](https://attack.mitre.org/)

## Project Status

**Status:** In Progress

**Project Category:** Blue Team / Security Operations

**Investigation Focus:** Windows Endpoint Security Monitoring

---

*This project is part of a practical Blue Team cybersecurity portfolio focused on developing log analysis, detection engineering and security investigation skills.*

**Disclaimer:** This project is conducted for educational and defensive cybersecurity purposes using authorised systems and security event data.
