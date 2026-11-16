# P4 — Threat Hunting in Windows Event Logs with Sigma Rules

## Project Overview

This project focuses on performing threat hunting across Windows Event Log (EVTX) files using **Chainsaw** and the community-maintained **SigmaHQ detection ruleset**.

The objective is to identify suspicious activities associated with different attacker techniques, investigate the corresponding event records, and map each detection to the MITRE ATT&CK framework.

The investigation uses publicly available Windows Event Log samples to demonstrate practical threat-hunting techniques and evidence-based security analysis.

## Problem Statement

Using Chainsaw and the SigmaHQ ruleset, hunt across the provided Windows Event Log sample dataset to identify at least five different attacker techniques.

For each identified detection:

- Identify the detected activity and relevant event evidence.
- Map the detection to its corresponding MITRE ATT&CK technique ID.
- Explain what the detected behaviour indicates.
- Assess its potential security significance.

## Tools & Resources

| Tool / Resource | Purpose |
|---|---|
| [Chainsaw](https://github.com/WithSecureLabs/chainsaw) | EVTX hunting and Sigma rule execution |
| [SigmaHQ](https://github.com/SigmaHQ/sigma) | Community detection rules |
| [EVTX-ATTACK-SAMPLES](https://github.com/sbousseaden/EVTX-ATTACK-SAMPLES) | Windows Event Log sample dataset |
| [MITRE ATT&CK](https://attack.mitre.org/) | Adversary technique identification and mapping |

## Investigation Objectives

1. Configure Chainsaw for Windows Event Log analysis.
2. Obtain and examine the provided EVTX sample dataset.
3. Execute Sigma-based detection hunts against the event logs.
4. Identify at least five distinct attacker techniques.
5. Map each detection to the appropriate MITRE ATT&CK technique ID.
6. Interpret the detection results and document their security implications.

## Submission Deliverables

### 1. Threat Hunt Report
A detailed investigation report documenting at least five detected attacker techniques, their supporting evidence, MITRE ATT&CK mappings, and explanations.

### 2. Screenshots
Screenshots demonstrating Chainsaw execution, Sigma-based detections, and relevant investigation evidence.

### 3. Chainsaw Output
Exported detection results in CSV and JSON formats for further analysis and documentation.

## Investigation Standards

All findings will be based on actual Chainsaw output and supporting Windows Event Log evidence. Detection matches will be investigated before being classified as suspicious activity. A rule match alone does not establish that a system was compromised.

## MITRE ATT&CK Mapping

Detected behaviours will be mapped to the relevant MITRE ATT&CK technique IDs using the official framework:

https://attack.mitre.org/

## Project Details

- **Project:** P4 — Threat Hunting in Windows Event Logs with Sigma Rules
- **Category:** Blue Team / Threat Hunting
- **Difficulty:** Intermediate
- **Primary Tools:** Chainsaw, SigmaHQ
- **Log Format:** Windows EVTX
- **Target:** At least five distinct attacker techniques

---

*Part of my Blue Team cybersecurity portfolio, focused on practical threat detection, event log investigation, and adversary behaviour analysis.*
