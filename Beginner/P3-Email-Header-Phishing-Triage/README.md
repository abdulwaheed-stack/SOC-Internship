# 📧 Email Header Analysis & Phishing Triage



## 📌 Project Overview

This project focuses on investigating suspicious email communications through email header analysis and phishing indicator identification.

Email-based attacks remain a common initial access technique used by threat actors. By examining email authentication mechanisms, sender information, routing details, and message metadata, security analysts can identify inconsistencies and indicators associated with phishing campaigns.

This investigation involves analyzing at least five real-world phishing email samples to evaluate their authenticity and identify potentially malicious characteristics.

## 🎯 Objectives

- Investigate real-world phishing email samples.
- Analyze email headers and message routing information.
- Examine SPF, DKIM, and DMARC authentication results.
- Compare sender addresses with Return-Path information.
- Identify spoofing indicators and suspicious email characteristics.
- Document phishing indicators and investigation findings.
- Develop recommendations for improving email security.

## 🧰 Tools & Technologies

| Tool | Purpose |
|---|---|
| Google Admin Toolbox | Email header analysis |
| MXToolbox | Email authentication and header inspection |
| Phishing Pot | Public phishing email samples |
| Text Editor | Inspecting raw email headers |

## 📂 Dataset & Resources

**Primary Dataset:** [Phishing Pot – GitHub](https://github.com/rf-peixoto/phishing_pot)

**Analysis Resources:**
- [Google Admin Toolbox – Message Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/)
- [MXToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)

The investigation uses publicly available phishing email samples for educational and defensive security analysis.

## 🔍 Investigation Methodology

The investigation follows a structured phishing triage workflow:

1. **Sample Collection:** Obtain at least five phishing email samples from the provided dataset.
2. **Header Extraction:** Extract and inspect the raw email headers.
3. **SPF Analysis:** Examine Sender Policy Framework authentication results.
4. **DKIM Analysis:** Evaluate DomainKeys Identified Mail signatures and verification results.
5. **DMARC Analysis:** Examine Domain-based Message Authentication, Reporting and Conformance results.
6. **Sender Verification:** Compare the From and Return-Path addresses for inconsistencies.
7. **Indicator Identification:** Investigate suspicious sender details, routing information, and authentication failures.
8. **Threat Assessment:** Evaluate the collected indicators and document the phishing characteristics of each sample.

## 🚨 Detection & Analysis Focus

| Indicator | Investigation Focus |
|---|---|
| SPF | Sender IP authorization |
| DKIM | Email signature verification |
| DMARC | Domain authentication policy and alignment |
| From Address | Claimed sender identity |
| Return-Path | Email return address |
| Received Headers | Email routing and originating infrastructure |
| Authentication Failures | Potential spoofing or unauthorized sending |

## 📊 Investigation Findings

Each of the five email samples will be examined individually.

Findings will include:
- Email authentication results.
- Sender and Return-Path comparison.
- Suspicious header characteristics.
- Identified phishing indicators.
- Overall assessment and supporting evidence.

**Note:** Actual findings and conclusions will be documented after completing the investigation.

## 📸 Evidence & Documentation

This directory will contain:

- Screenshots of email header analysis.
- Authentication verification results.
- Relevant email header extracts.
- Individual phishing sample analysis.
- Final Phishing Triage Report in PDF format.

## 🔐 Security Recommendations

Potential defensive recommendations based on the investigation may include:

- Enforce SPF, DKIM, and DMARC policies.
- Monitor email authentication failures.
- Implement email security gateways.
- Educate users about phishing indicators.
- Investigate suspicious sender domains.
- Establish procedures for reporting suspicious emails.

## 📚 References

- [Phishing Pot – GitHub](https://github.com/rf-peixoto/phishing_pot)
- [Google Admin Toolbox](https://toolbox.googleapps.com/apps/messageheader/)
- [MXToolbox](https://mxtoolbox.com/EmailHeaders.aspx)

## 👨‍💻 Internship Information

**Organization:** CyberSNova  
**Program:** Blue Team Cybersecurity Internship  
**Level:** Beginner  
**Project:** Email Header Analysis & Phishing Triage

---

*This project is conducted for educational and defensive cybersecurity purposes using publicly available phishing email samples.*
