# Analysis & Investigation Documentation

## Overview

This directory contains the analytical documentation, investigation notes, event records, and detection logic developed as part of the Linux System Log Analysis project.

The objective is to examine Linux authentication logs, identify suspicious activity, investigate SSH authentication patterns, and document findings using a structured SOC investigation workflow.

All conclusions are based on observed log evidence and documented analysis.

## Analysis Files

| File | Description |
|---|---|
| `investigation-notes.md` | Records the investigation methodology, analysis steps, observations, and analyst notes. |
| `findings.csv` | Maintains structured records of identified security findings. |
| `ssh-authentication-analysis.md` | Documents the examination of SSH authentication activity, including failed and successful login attempts. |
| `event-timeline.csv` | Organizes relevant security events chronologically for investigation and correlation. |
| `detection-logic.md` | Describes the detection criteria and analytical logic used to identify suspicious authentication patterns. |

## Investigation Scope

The analysis focuses on:

- Failed SSH authentication attempts
- Successful SSH authentication events
- Repeated login attempts against user accounts
- Potential brute-force activity
- Suspicious source IP addresses
- Unusual authentication patterns
- Relevant timestamps and event sequences

## Investigation Methodology

The investigation follows a structured process:

1. **Log Collection:** Identify and obtain the Linux authentication log dataset.
2. **Log Examination:** Review authentication records and extract relevant SSH events.
3. **Pattern Identification:** Examine repeated failures, account targeting, and unusual activity.
4. **Event Correlation:** Compare timestamps, source addresses, usernames, and authentication outcomes.
5. **Detection Analysis:** Apply appropriate detection criteria to identify potentially suspicious behavior.
6. **Documentation:** Record observations, supporting evidence, and security recommendations.

## Evidence & Accuracy

All findings must be supported by actual log records.

- Observed events are distinguished from suspected malicious activity.
- Event timestamps and source addresses are preserved where available.
- Detection conclusions are not treated as confirmed incidents without sufficient evidence.
- Missing or unavailable information is explicitly documented.

## Investigation Status

**Status:** In Progress

The analysis documents will be updated as the investigation progresses and verified findings become available.

## Related Documentation

- [Project Overview](../README.md)
- [Investigation Notes](investigation-notes.md)

## Project Classification

- **Domain:** Blue Team Operations
- **Focus Area:** Linux Log Analysis
- **Security Function:** Security Monitoring & Detection
- **Investigation Type:** Authentication Log Analysis
