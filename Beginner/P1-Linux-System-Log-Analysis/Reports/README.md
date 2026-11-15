**# SSH AUTHENTICATION THREAT INVESTIGATION
### An Evidence-Led Analysis of Linux OpenSSH Authentication Logs

**Project:** P1 – Linux System Log Analysis  
**Domain:** Blue Team | Security Operations | Threat Detection  
**Investigation:** SSH Authentication Abuse  
**Dataset:** LogHub – OpenSSH (`SSH.log`)  
**Analysis Environment:** Windows PowerShell  
**Report Date:** 15 November 2026  
**Classification:** Technical Security Investigation – Training Environment

---

# 01. Executive Summary

Secure Shell (SSH) is a fundamental component of Linux infrastructure. It enables administrators, developers and automated systems to access remote machines. However, when exposed to untrusted networks, SSH services can become targets for automated credential-guessing activity.

This investigation examines authentication activity within an OpenSSH log dataset to identify suspicious access patterns, frequently targeted accounts, high-volume source addresses and successful authentication events.

The analysis began with a review of 655,147 log lines. Authentication records were extracted and examined using Windows PowerShell, followed by username frequency analysis, source IP aggregation and correlation between failed and successful password authentication.

The investigation identified 197,587 matching failed-password records and 182 matching successful-password records. One particularly significant observation was the concentration of failed authentication activity against the Linux `root` account, which accounted for approximately 89.5% of the failed-password records.

The investigation also identified eight source IP addresses appearing in both failed and successful password authentication records.

These findings are consistent with substantial SSH authentication abuse and possible automated password guessing. However, the available evidence does not establish that the observed activity resulted in unauthorized system access.

**Investigation outcome:** Significant authentication abuse indicators identified. Further investigation is recommended. System compromise remains unconfirmed.

---

# 02. Background and Threat Context

SSH authentication attacks are not limited to individual login attempts. Automated tools can repeatedly attempt credentials against exposed services, target common usernames, distribute attempts across multiple source addresses or use previously compromised credentials.

Three relevant attack patterns are worth understanding.

**Password guessing:** Repeatedly attempting passwords against an account, often using common or predictable credentials.

**Password spraying:** Attempting a small number of common passwords against multiple accounts to avoid triggering account-specific protections.

**Credential stuffing:** Testing previously exposed username-password combinations against another service.

MITRE ATT&CK classifies these behaviours under:

- **T1110 – Brute Force**
- **T1110.001 – Password Guessing**
- **T1110.003 – Password Spraying**
- **T1110.004 – Credential Stuffing**

The observed repeated failures and username targeting in this investigation are relevant to the password-guessing technique. The other sub-techniques are included as threat context, not as confirmed behaviours in this dataset.

Reference: [MITRE ATT&CK – Brute Force](https://attack.mitre.org/techniques/T1110/)

---

# 03. Investigation Scope and Dataset

The investigation used the supplied LogHub OpenSSH dataset.

| Parameter | Value |
|---|---|
| Dataset file | SSH.log |
| Total log lines | 655,147 |
| Failed-password matching records | 197,587 |
| Successful-password matching records | 182 |
| Analysis platform | Windows PowerShell |
| Log source | OpenSSH authentication logs |

### Investigation objectives

The analysis was designed to answer the**
