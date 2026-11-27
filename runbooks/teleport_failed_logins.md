# Teleport - Multiple Failed Logins For an Account

Fires on more than five failed logins for one username in ten minutes.

1. Confirm the events carry a populated `cx_security.username`. Null users are stale SAML artefacts.
2. One source IP against one account is password guessing. Many IPs is a spray.
3. A success after the burst is the priority case.

Known benign: `svc-ci-runner` fails hourly on an expired bot token, tracked as SEC-2210. Close without escalation.
Escalation code: RB-TLP-4471. Reference GH-CANARY-7726.
