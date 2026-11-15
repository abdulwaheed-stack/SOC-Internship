# Evidence Repository

## Overview

This directory contains the supporting evidence collected during the Linux System Log Analysis investigation.

Evidence is maintained to support analytical observations, validate suspicious authentication patterns, and provide traceability between raw log records and documented findings.

## Evidence Categories

| Evidence File | Description |
|---|---|
| `failed-login-events.csv` | Extracted records of failed authentication attempts. |
| `successful-login-events.csv` | Extracted records of successful authentication events. |
| `suspicious-events.txt` | Relevant raw log entries selected for further investigation. |

## Evidence Handling

- Preserve original log records wherever possible.
- Maintain timestamps and source IP addresses.
- Avoid modifying original evidence.
- Record the source of each extracted event.
- Ensure findings can be traced back to supporting log entries.
- Sanitize sensitive information before publishing evidence.

## Evidence Status

**Status:** Pending collection and validation.

Evidence files will be added as the investigation progresses.

## Important Note

Only genuine records obtained from the analyzed dataset will be included. No fabricated events or investigation results will be presented.
