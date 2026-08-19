# CS-03 — Phishing Awareness Kit Architecture

## 1. Architecture Objective

The CS-03 Phishing Awareness Kit is designed as a controlled security-awareness laboratory that demonstrates the complete lifecycle of a phishing-awareness exercise.

The architecture follows:

**Threat → Simulation → User Interaction → Awareness Intervention → Measurement → SOC Analysis → Remediation**

All phishing activity is restricted to authorized laboratory users and infrastructure.

---

## 2. High-Level Architecture

```text
                         NCRYPT0EDGE PHISHING AWARENESS LAB
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │      ATTACK SCENARIO    │
                         │                         │
                         │  Simulated Phishing     │
                         │  MITRE ATT&CK: T1566   │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │        GoPhish          │
                         │                         │
                         │ • Users & Groups        │
                         │ • Email Templates       │
                         │ • Landing Pages         │
                         │ • Campaigns             │
                         │ • Tracking              │
                         └────────────┬────────────┘
                                      │
                              Controlled Email
                                      │
                                      ▼
                  ┌────────────────────────────────────┐
                  │          AUTHORIZED TEST USER      │
                  │                                    │
                  │          Test Mailbox              │
                  │                                    │
                  │       No real credentials          │
                  └────────────────┬───────────────────┘
                                   │
                         ┌─────────┴─────────┐
                         │                   │
                       Opens              Clicks
                         │                   │
                         └─────────┬─────────┘
                                   ▼
                         ┌─────────────────────────┐
                         │    AWARENESS PAGE       │
                         │                         │
                         │ • Simulation notice     │
                         │ • Phishing red flags    │
                         │ • Correct response      │
                         │ • Reporting procedure   │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │        METRICS          │
                         │                         │
                         │ • Delivery              │
                         │ • Opens                 │
                         │ • Clicks                │
                         │ • Reports               │
                         │ • Failure rate          │
                         │ • Improvement            │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │      SOC ANALYSIS       │
                         │                         │
                         │ • T1566 mapping         │
                         │ • IOC analysis           │
                         │ • Reporting workflow    │
                         │ • Defensive controls    │
                         │ • Recommendations       │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │    AWARENESS PROGRAM    │
                         │                         │
                         │ Training                │
                         │ Reporting Procedure     │
                         │ Remediation             │
                         └─────────────────────────┘
...
