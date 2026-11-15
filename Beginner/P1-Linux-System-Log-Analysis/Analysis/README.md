Objective: Investigate SSH authentication activity.



Dataset: LogHub OpenSSH dataset (SSH.log).



Environment: Windows PowerShell.



Dataset size: 655,147 log lines.



Analysis performed: Failed logins, targeted usernames, source IPs, successful logins, and IP correlation.



Key observation: 197,587 failed-password matching records and 182 successful-password matching records.



Limitations: Aggregated log messages mean record counts may not equal actual authentication attempts.



Output: findings.csv containing 14 structured findings.
