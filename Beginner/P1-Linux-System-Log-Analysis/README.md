# 🛡️ Linux System Log Analysis & Suspicious Activity Investigation


## 📌 Project Overview

This project focuses on the investigation and analysis of Linux system logs to identify suspicious authentication activity, detect potential SSH brute-force attempts, and uncover anomalous login behaviour.

System logs provide valuable forensic evidence of activities occurring on a Linux host. By examining authentication events, login timestamps, source IP addresses, and access patterns, this investigation aims to identify potentially malicious activity and distinguish legitimate user behaviour from suspicious events.

The investigation uses publicly available sample datasets to simulate a real-world Security Operations Center (SOC) log analysis workflow.

## 🎯 Objectives

- Analyze Linux system and OpenSSH authentication logs.
- Identify repeated SSH login failures and potential brute-force activity.
- Differentiate successful and unsuccessful authentication attempts.
- Investigate suspicious source IP addresses and login patterns.
- Identify unusual authentication activity using timestamps and event frequency.
- Document findings and provide security recommendations.

## 🧰 Tools & Technologies

| Tool | Purpose |
|---|---|
| Linux Terminal | Log investigation and analysis |
| grep | Filtering relevant log entries |
| awk | Extracting and processing log fields |
| LogHub | Public security log datasets |
| Text Editor | Reviewing and documenting findings |

## 📂 Dataset & Resources

**Primary Dataset:** [LogHub – A Large Collection of System Log Datasets](https://github.com/logpai/loghub)

Relevant datasets:
- Linux System Logs
- OpenSSH Logs

The investigation uses publicly available sample log data for security analysis and educational purposes.

## 🔍 Investigation Methodology

The investigation follows a structured log analysis workflow:

1. **Log Collection:** Obtain Linux and OpenSSH sample log files from LogHub.
2. **Log Inspection:** Examine authentication records and understand their structure.
3. **Event Filtering:** Use grep and awk to isolate relevant authentication events.
4. **Failed Login Analysis:** Identify repeated authentication failures and suspicious login attempts.
5. **Successful Login Analysis:** Examine successful authentication events and their associated timestamps and source identifiers.
6. **Anomaly Identification:** Investigate unusual login frequency, repeated attempts, and potentially suspicious IP addresses.
7. **Documentation:** Record relevant evidence, observations, findings, and recommendations.

## 🚨 Detection Focus

| Security Activity | Investigation Focus |
|---|---|
| SSH Brute-Force Attempts | Repeated failed authentication attempts |
| Failed Logins | Unsuccessful authentication events |
| Successful Logins | Valid authentication activity |
| Suspicious IP Addresses | Sources associated with unusual login patterns |
| Authentication Anomalies | Unusual login frequency and timing |

## 📊 Findings & Analysis

Investigation findings will be documented with supporting log evidence, timestamps, source identifiers, and explanations of suspicious activity.

Each identified event will be evaluated based on its context rather than automatically classified as malicious.

**Note:** Actual findings and conclusions will be added after completing the investigation.

## 📸 Evidence & Documentation

This directory will contain:

- Screenshots of terminal-based log analysis.
- Relevant filtered log entries.
- Commands and analysis outputs.
- Documented suspicious events.
- Final investigation report in PDF format.

## 🔐 Security Recommendations

Potential defensive recommendations based on the investigation may include:

- Implement SSH key-based authentication.
- Disable unnecessary password-based SSH access.
- Apply account lockout or rate-limiting controls.
- Monitor repeated authentication failures.
- Restrict SSH access to trusted sources where appropriate.
- Centralize authentication logs for continuous monitoring.

## 📚 References

- [LogHub – System Log Datasets](https://github.com/logpai/loghub)
- [OpenSSH Documentation](https://www.openssh.com/manual.html)
- [Linux Manual Pages](https://man7.org/linux/man-pages/)

## 👨‍💻 Internship Information

**Organization:** CyberSNova  
**Program:** Blue Team Cybersecurity Internship  
**Level:** Beginner  
**Project:** Linux System Log Analysis

---

*This project is conducted in a controlled educational environment using publicly available sample datasets. All findings will be based on actual investigation evidence.*
