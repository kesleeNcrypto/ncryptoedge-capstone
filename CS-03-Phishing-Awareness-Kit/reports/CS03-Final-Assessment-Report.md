# CS-03 --- Phishing Awareness Kit

## Final Assessment Report

**Project:** CS-03 Phishing Awareness Kit\
**Organization:** NcryptoEdge\
**Author:** Esla Kwanza\
**Context:** Controlled laboratory validation for Nigerian SMEs and
hospitality organizations\
**Assessment Type:** Technical / Security Awareness Capability
Validation\
**Assessment Period:** August 2026\
**Status:** Final Baseline Validation

------------------------------------------------------------------------

# Executive Summary

CS-03 is a controlled, self-hosted phishing-awareness capability
developed by NcryptoEdge for Nigerian SMEs and hospitality
organizations.

The project implements a four-phase lifecycle:

``` text
TRAIN → SIMULATE → MEASURE → RESPOND
```

The laboratory combines GoPhish for phishing simulation with Mailpit for
local SMTP capture and a synthetic test recipient. The validated
campaign demonstrated the baseline pipeline from email delivery through
user interaction and GoPhish event tracking.

## Validated Results

  Metric                    Result
  ----------------------- --------
  Synthetic recipients           1
  Emails sent                    1
  Emails opened                  1
  Links clicked                  1
  Submitted data                 0
  Credentials collected          0
  Emails reported                0

The result demonstrates that the technical phishing-awareness simulation
pipeline is operational.

**Important limitation:** this was a single-recipient synthetic
laboratory validation. It must not be interpreted as an employee
phishing-susceptibility rate or organizational risk statistic.

------------------------------------------------------------------------

# 1. Project Overview

## 1.1 Problem Statement

Phishing and social engineering target human decision-making and remain
practical attack paths for organizations.

For Nigerian SMEs, relevant scenarios include banking alerts, vendor
invoices, hotel reservations, OTA complaints, government or regulatory
impersonation, executive impersonation, job-related scams, and
SMS/messaging-platform phishing.

CS-03 addresses this through a repeatable security-awareness capability
using free or open-source tooling.

## 1.2 Objectives

1.  Demonstrate a controlled phishing-simulation pipeline.
2.  Provide structured security-awareness training.
3.  Measure user interaction with simulated phishing content.
4.  Provide a defined phishing incident-response workflow.
5.  Produce auditable technical evidence.
6.  Establish a foundation for future authorized organizational
    campaigns.

------------------------------------------------------------------------

# 2. Scope

## In Scope

-   GoPhish deployment and configuration.
-   Local SMTP delivery through Mailpit.
-   Synthetic test recipient.
-   Phishing email template.
-   GoPhish landing page.
-   Tracking URL.
-   Campaign telemetry.
-   Security-awareness training.
-   Pre/post knowledge assessment.
-   Metrics framework.
-   Incident-response guidance.
-   Evidence collection.
-   MITRE ATT&CK alignment.
-   Final documentation.

## Out of Scope

The baseline validation does not claim:

-   Real employee susceptibility measurements.
-   Production organizational deployment.
-   External email delivery.
-   Credential harvesting.
-   Real credential collection.
-   Wazuh alert validation.
-   Automated SOAR response.
-   Production endpoint compromise.
-   Real-world victimization.

------------------------------------------------------------------------

# 3. Laboratory Architecture

``` text
                         CS-03 PHISHING AWARENESS KIT

                              ┌─────────────┐
                              │   GoPhish   │
                              │ Admin :3333 │
                              │ Phish :80   │
                              └──────┬──────┘
                                     │
                              SMTP :1025
                                     │
                                     ▼
                              ┌─────────────┐
                              │   Mailpit   │
                              │  Web :8025  │
                              └──────┬──────┘
                                     │
                                     ▼
                              Synthetic User
                                     │
                                     ▼
                               Tracking URL
                                     │
                                     ▼
                         CS03 Training Landing Page
                                     │
                                     ▼
                              GoPhish Event
                                     │
                                     ▼
                              Campaign Metrics
```

## Components

  Component                 Purpose                       Status
  ------------------------- ----------------------------- ------------------------
  Kali Linux                Laboratory host               Validated
  GoPhish v0.12.1           Phishing simulation           Validated
  GoPhish Admin             Campaign administration       Validated
  GoPhish phishing server   Landing-page delivery         Validated
  Mailpit                   Local SMTP capture            Validated
  Synthetic user            Safe test recipient           Validated
  Landing page              Awareness destination         Validated
  GoPhish telemetry         Interaction measurement       Validated
  Wazuh                     Future endpoint correlation   Not baseline-validated

------------------------------------------------------------------------

# 4. Campaign Configuration

**Campaign:** `CS03-Local-Pipeline-Test`\
**Email Template:** `CS03-Lab-Test-Email`\
**Subject:** `NcryptoEdge Security Awareness Test`\
**Landing Page:** `CS03-Lab-Landing-Page`\
**Group:** `LAB-Test-User`\
**Recipient:** `lab-user@local.test`\
**Sending Profile:** `Local-Lab`\
**SMTP:** `127.0.0.1:1025`

The recipient was synthetic and existed only for laboratory validation.

------------------------------------------------------------------------

# 5. Campaign Methodology

``` text
Configure GoPhish
       ↓
Configure Mailpit
       ↓
Create email template
       ↓
Create landing page
       ↓
Create synthetic recipient
       ↓
Configure local sending profile
       ↓
Launch campaign
       ↓
Receive email in Mailpit
       ↓
Open campaign email
       ↓
Follow tracking URL
       ↓
Load landing page
       ↓
Validate GoPhish telemetry
```

The campaign was restricted to the controlled laboratory environment.

------------------------------------------------------------------------

# 6. Validation Results

## 6.1 Observed Events

  Event              Result
  ---------------- --------
  Email Sent              1
  Email Opened            1
  Link Clicked            1
  Submitted Data          0
  Credentials             0
  Email Reported          0

## 6.2 Technical Interpretation

The validation demonstrated:

-   SMTP delivery.
-   Mailpit message capture.
-   Email opening.
-   Tracking-link functionality.
-   Landing-page delivery.
-   GoPhish event recording.
-   Campaign dashboard measurement.

No credentials were collected.

## 6.3 Click Rate

``` text
Click Rate = Clicked / Delivered × 100
Click Rate = 1 / 1 × 100
Click Rate = 100%
```

This is a **technical validation result only**. With n=1, it is not an
organizational susceptibility benchmark.

------------------------------------------------------------------------

# 7. Evidence Register

The repository contains evidence generated during the validated
campaign.

  ID     Artifact                Purpose
  ------ ----------------------- ---------------------------------
  E-01   Mailpit email           Successful local SMTP delivery
  E-02   Landing page            Successful campaign destination
  E-03   GoPhish click event     Recorded user interaction
  E-04   Campaign dashboard      Campaign-level telemetry
  E-05   Clicked-link evidence   End-to-end interaction path

Evidence is stored under:

``` text
evidence/
```

------------------------------------------------------------------------

# 8. Security Controls

  Control                             Status
  ----------------------------------- ---------------
  Authorized laboratory environment   Implemented
  Synthetic recipient                 Implemented
  Local SMTP capture                  Implemented
  External SMTP delivery              Not used
  Real credentials                    Not collected
  Password capture                    Disabled
  Production identities               Not used
  Evidence collection                 Implemented
  Campaign telemetry                  Implemented

The baseline exercise deliberately avoids unnecessary sensitive-data
collection.

------------------------------------------------------------------------

# 9. Security Awareness Training

CS-03 contains six training modules:

``` text
1. Phishing Fundamentals
2. Identify Phishing
3. SLAM
4. STOP
5. Reporting & Response
6. Social Engineering Beyond Email
```

The program teaches users to inspect senders, links, attachments and
messages using SLAM and to respond safely using STOP.

## Training Lifecycle

``` text
Pre-Assessment
      ↓
Training
      ↓
Phishing Simulation
      ↓
Measurement
      ↓
Educational Feedback
      ↓
Post-Assessment
      ↓
Incident-Response Exercise
      ↓
Periodic Review
```

------------------------------------------------------------------------

# 10. Pre/Post Assessment

The project includes a 10-question knowledge assessment covering:

-   OTP requests.
-   Vendor invoices.
-   Sender verification.
-   Suspicious links.
-   Urgency.
-   Attachments.
-   Executive impersonation.
-   Post-click response.
-   Reporting.
-   Social engineering.

The assessment measures knowledge separately from behavioral simulation.

``` text
Knowledge
   +
Observed Behavior
   ↓
Security Awareness Assessment
```

No organizational assessment scores are claimed in this baseline report
because the validated campaign used a synthetic recipient.

------------------------------------------------------------------------

# 11. Metrics Framework

The CS-03 framework defines:

-   Delivery Rate.
-   Open Rate.
-   Click Rate.
-   Credential Submission Rate.
-   Report Rate.
-   Time-to-Report.
-   Repeat Clicker Rate.
-   Department Click Rate.
-   Training Impact.

For this baseline, only directly observed GoPhish events are reported.

Repeated authorized campaigns should be used for trend analysis rather
than treating a single campaign as definitive risk measurement.

------------------------------------------------------------------------

# 12. Incident Response

The project playbook uses four severity levels:

  Severity   Condition                                    Response
  ---------- -------------------------------------------- ------------------------
  P1         Credentials submitted + privileged account   Immediate
  P2         Credentials submitted + standard account     Within 1 hour
  P3         Link clicked, no credentials                 Within 4 hours
  P4         Email reported, not clicked                  Review within 24 hours

The validated campaign produced:

``` text
Link clicked
+
No credentials submitted
```

This corresponds to the P3 scenario.

A P3 response includes validation, determining whether content was
downloaded or executed, endpoint assessment, security scanning, review
for suspicious persistence/network activity, recovery, and escalation if
compromise is discovered.

------------------------------------------------------------------------

# 13. MITRE ATT&CK Alignment

  -----------------------------------------------------------------------
  Technique               Name                    CS-03 Relevance
  ----------------------- ----------------------- -----------------------
  T1566.001               Phishing: Spearphishing Training / future
                          Attachment              scenario

  T1566.002               Phishing: Spearphishing **Validated baseline
                          Link                    simulation path**

  T1566.003               Phishing: Spearphishing Training / future
                          via Service             scenario

  T1204.002               User Execution:         Training / future
                          Malicious File          scenario

  T1078                   Valid Accounts          Credential-compromise
                                                  scenario / future
                                                  exercise
  -----------------------------------------------------------------------

The baseline campaign specifically validates the simulated-link path
associated with **T1566.002**.

The other techniques are documented as relevant scenarios and are not
claimed as independently validated by this campaign.

------------------------------------------------------------------------

# 14. Findings

## Finding 1 --- Simulation Pipeline Operational

**Severity:** Informational / Capability Validation

The GoPhish → Mailpit → synthetic user → landing page → telemetry
pipeline operated successfully.

**Evidence:** E-01 through E-05.

**Status:** Validated.

## Finding 2 --- User Interaction Measured

The system recorded an email open and link click for the synthetic
recipient.

**Status:** Validated.

## Finding 3 --- No Credentials Collected

The baseline campaign recorded zero submitted data and zero credentials.

**Status:** Validated.

## Finding 4 --- Awareness and Response Materials Integrated

The project combines simulation with training, assessment, metrics,
evidence and incident response.

**Status:** Documented capability validated.

------------------------------------------------------------------------

# 15. Limitations

### Sample Size

The validation used one synthetic recipient. Statistical conclusions
about organizational behavior cannot be drawn.

### Controlled Environment

The campaign used local SMTP capture. Real-world mail-delivery behavior
may differ.

### No Credential Capture

Credential submission was not part of the baseline validation.

### No Endpoint Correlation

Wazuh integration is a future enhancement. No Wazuh alert is claimed in
this baseline report.

### No Production Campaign

The project does not claim to have assessed real employees or a
production organization.

------------------------------------------------------------------------

# 16. Recommendations

## Immediate

1.  Preserve the validated laboratory as the CS-03 reference
    implementation.
2.  Maintain the evidence register for every future campaign.
3.  Continue using synthetic recipients during development and testing.
4.  Keep credential capture disabled unless explicitly authorized.
5.  Use the six-module curriculum as the baseline awareness program.

## Short Term

1.  Conduct a larger authorized simulation.
2.  Introduce vendor-invoice, executive-impersonation and OTA scenarios.
3.  Measure reporting behavior.
4.  Run pre/post knowledge assessments.
5.  Compare campaign results over time.

## Future Technical Expansion

1.  Integrate GoPhish telemetry with Wazuh.
2.  Correlate phishing interaction with endpoint events.
3.  Create SOC detection rules.
4.  Integrate case management.
5.  Automate notification and response workflows.
6.  Build an executive phishing-risk dashboard.

These are future enhancements and are outside the baseline validation
claim.

------------------------------------------------------------------------

# 17. Business Application

CS-03 is designed as a reusable security-awareness capability for
Nigerian SMEs.

Potential environments include:

-   Hotels.
-   Professional services.
-   Schools.
-   NGOs.
-   Clinics.
-   Small financial or fintech organizations.
-   Other SMEs without dedicated security teams.

A production service can combine:

``` text
Awareness Training
       +
Authorized Phishing Simulation
       +
Metrics
       +
Incident Response
       +
Executive Reporting
```

This creates a repeatable security-awareness service rather than a
one-time technical demonstration.

------------------------------------------------------------------------

# 18. Project Deliverables

``` text
CS-03-Phishing-Awareness-Kit/
│
├── README.md
├── docs/
│   ├── architecture.md
│   ├── attack-mapping.md
│   ├── deployment.md
│   ├── campaign-methodology.md
│   ├── metrics.md
│   ├── incident-response.md
│   ├── lessons-learned.md
│   └── project-scope.md
│
├── campaigns/
│   └── CS03-Local-Pipeline-Test.md
│
├── training/
│   ├── modules.md
│   └── pre-post-assessment.md
│
├── detections/
│   └── wazuh/
│
├── evidence/
│   ├── E-01-mailpit-email.png
│   ├── E-02-landing-page.png
│   ├── E-03-gophish-click-event.png
│   ├── E-04-campaign-dashboard.png
│   ├── E-05-clicked-link.png
│   └── README.md
│
├── reports/
│   └── CS03-Final-Assessment-Report.md
│
└── scripts/
```

------------------------------------------------------------------------

# 19. Conclusion

CS-03 successfully demonstrates a controlled phishing-awareness
laboratory built around open-source, self-hosted tooling.

The validated baseline demonstrated:

``` text
Email Delivery
      ↓
Email Opening
      ↓
Tracking Link
      ↓
Landing Page
      ↓
User Interaction
      ↓
Campaign Telemetry
```

The project extends beyond simulation through structured awareness
training, knowledge assessment, metrics, incident response, evidence
management and MITRE ATT&CK alignment.

The key result is not the 100% click rate produced by one synthetic
recipient.

The key result is that **the complete security-awareness simulation
pipeline works and is documented well enough to be repeated,
demonstrated, measured and expanded.**

CS-03 therefore establishes a practical foundation for future authorized
organizational campaigns and broader security-operations integration.

------------------------------------------------------------------------

# Appendix A --- Validated Campaign Summary

``` text
Campaign:
CS03-Local-Pipeline-Test

Recipient:
lab-user@local.test

Sending Profile:
Local-Lab

SMTP:
127.0.0.1:1025

Landing Page:
CS03-Lab-Landing-Page

Results:
Email Sent       1
Email Opened     1
Link Clicked     1
Submitted Data   0
Credentials      0
Reported         0
```

# Appendix B --- Evidence

  ID     Evidence                Demonstrates
  ------ ----------------------- ------------------------
  E-01   Mailpit email           SMTP delivery
  E-02   Landing page            Campaign destination
  E-03   GoPhish click event     Interaction telemetry
  E-04   Campaign dashboard      Campaign measurement
  E-05   Clicked-link evidence   End-to-end interaction

# Appendix C --- Demo Sequence

Recommended demonstration:

``` text
1. Introduce CS-03
2. Show architecture
3. Show GoPhish configuration
4. Show Mailpit
5. Open the simulated email
6. Open the training page
7. Show GoPhish results
8. Show evidence
9. Show training / IR documentation
10. Summarize results and limitations
```

**Recommended demo duration: 5--7 minutes.**

# Appendix D --- Final Validation Statement

> CS-03 was validated as a controlled laboratory phishing-awareness
> pipeline using GoPhish, Mailpit, a synthetic recipient, a simulated
> email, a GoPhish landing page, and campaign telemetry.

> The validation demonstrated successful email delivery, opening, link
> tracking, landing-page interaction and campaign measurement without
> collecting real credentials.

> Organizational risk conclusions require a larger, explicitly
> authorized deployment and repeated measurement.

------------------------------------------------------------------------

**End of Report**

*CS-03 Phishing Awareness Kit --- NcryptoEdge*\
*Security Operations. Built for African Business.*
