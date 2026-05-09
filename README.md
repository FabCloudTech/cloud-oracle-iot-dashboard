# The Cloud Oracle — AI-Enhanced IoT Security Monitoring Dashboard

**Project Type:** IoT Security | AI Anomaly Detection | Real-Time Monitoring  
**Environment:** Python, WebSocket, MQTT, scikit-learn  
**Simulated Org:** Hydroficient Hotel IoT Water System  
**Recognition:** Top Performer — Top 10% of all Hydroficient Extern participants

---

## Overview

The Cloud Oracle is a live IoT security monitoring dashboard built as the capstone project for the Hydroficient IoT Cyber Defense Externship. It processes real sensor data via WebSocket, validates every incoming message using a layered security stack, and displays real-time attack detection across 3 hotel zones. An Isolation Forest machine learning model was integrated on top of the rule-based validation layer to catch behavioral anomalies that rules alone cannot detect.

---

## What I Built

### 1. Real-Time Security Validation Pipeline

Every message processed by the dashboard passes through three sequential security checks before being accepted:

- **HMAC-SHA256 verification** — confirms message authenticity and integrity
- **Timestamp freshness check** — rejects replayed or delayed messages outside the acceptable window
- **Sequence number tracking** — detects out-of-order or duplicate messages indicating replay attacks

### 2. Isolation Forest AI Anomaly Detection

Integrated scikit-learn's Isolation Forest model on top of the rule-based layer to detect subtle behavioral anomalies in sensor data patterns — catches what rules miss.

**Model Performance:**

| Metric | Score |
|---|---|
| Precision | 0.736 |
| Recall | 0.789 |
| F1 Score | 0.757 |

### 3. Full Experiment Results

| Metric | Result |
|---|---|
| Valid messages accepted | 1,030 |
| Attacks blocked | 30 |
| False negatives | 0 |

Zero false negatives — no attack slipped through undetected.

### 4. Dashboard Features

- Live WebSocket feed displaying sensor data across 3 hotel zones
- Real-time attack detection alerts with zone card glow animations
- AI anomaly event log with dedicated stat counter
- Branded "The Cloud Oracle" UI with custom SVG logo

---

## Architecture

```
MQTT Sensor Simulation
        ↓
MQTT Broker
        ↓
Subscriber (subscriber_dashboard_ai.py)
    - HMAC-SHA256 validation
    - Timestamp freshness check
    - Sequence number tracking
    - Isolation Forest AI model
        ↓
WebSocket Server (dashboard_server_ai.py)
        ↓
Cloud Oracle Dashboard (dashboard-oracle.html)
    - Real-time zone monitoring
    - Attack alerts
    - AI anomaly detection feed
```

---

## Tech Stack

`Python` `WebSocket` `MQTT` `HMAC-SHA256` `Isolation Forest` `scikit-learn` `Anomaly Detection` `Machine Learning` `IoT Security` `Real-Time Monitoring`

---

## Frameworks Referenced

- IEC 62443 IoT Security Standards
- AWS IoT Core architecture patterns

---

## Recognition

Earned **Top Performer** designation upon completion of the Hydroficient IoT Cyber Defense Externship — awarded to the top 10% of all participants across the program.
