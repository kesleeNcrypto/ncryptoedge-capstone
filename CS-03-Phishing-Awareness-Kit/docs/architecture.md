# CS-03 — Phishing Awareness Kit Architecture

## 1. Architecture Objective

The CS-03 Phishing Awareness Kit is designed as a controlled security-awareness laboratory that demonstrates the complete lifecycle of a phishing-awareness exercise.

The architecture follows:

**Threat → Simulation → User Interaction → Awareness Intervention → Measurement → SOC Analysis → Remediation**

All phishing activity is restricted to authorized laboratory users and infrastructure.

---

## 2. Validated Laboratory Architecture

```text
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
Eof
