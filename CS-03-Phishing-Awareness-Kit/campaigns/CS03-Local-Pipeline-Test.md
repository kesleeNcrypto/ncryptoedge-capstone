# CS03 — Local Pipeline Test

## Objective

Validate the complete local phishing-awareness pipeline using authorized laboratory infrastructure.

## Pipeline

GoPhish
↓
SMTP
↓
Mailpit
↓
Test Mailbox
↓
Controlled Link Interaction
↓
Awareness Landing Page
↓
GoPhish Event
↓
Evidence
↓
SOC Analysis

## Test Scope

- Authorized laboratory environment
- Test user only
- No real credentials
- No external recipients
- No malware
- No uncontrolled phishing activity

## Test Components

| Component | Status |
|---|---|
| Kali Linux | Pending |
| GoPhish | Pending |
| Mailpit | Pending |
| Test mailbox | Pending |
| Email template | Pending |
| Landing page | Pending |
| Campaign | Pending |
| Click event | Pending |
| Evidence | Pending |
| Metrics | Pending |

## Success Criteria

The test is successful when:

1. GoPhish is operational.
2. A controlled email is generated.
3. Mailpit receives the email.
4. The test user can access the message.
5. The simulated link is clicked.
6. GoPhish records the interaction.
7. The awareness page is displayed.
8. Evidence is captured.
9. The result is documented.

## MITRE ATT&CK

Primary technique:

**T1566 — Phishing**

Specific sub-technique will be documented according to the final campaign design.

## Result

Pending execution.
