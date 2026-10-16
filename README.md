<div align="center">

# 🚗 Tester Present (0x3E) in UDS

### Interactive UDS Diagnostic Session Simulator

A browser-based educational tool demonstrating how the  
**Tester Present service (0x3E)** supports diagnostic-session continuity.

## 🎮 [Launch the Interactive Simulator](https://anandgonnagar.github.io/tester-present-uds/)

</div>

---

## 📖 Overview

**Tester Present**, UDS service identifier `0x3E`, is used by a diagnostic client to indicate continued presence during diagnostic communication.

This interactive web application demonstrates the relationship between:

- Diagnostic Session Control
- Programming and Extended Diagnostic Sessions
- Tester Present requests
- Positive-response suppression
- Illustrative session-maintenance behavior
- Adaptive AUTOSAR diagnostic service handling

> [!IMPORTANT]
> Tester Present helps maintain an already established diagnostic session.  
> It does not create, restore, or unlock a diagnostic session.

---

## ✨ Features

| Feature | Demonstration |
|---|---|
| Default Session | Initial diagnostic server state |
| Programming Session | `10 02` → `50 02` |
| Extended Diagnostic Session | `10 03` → `50 03` |
| Tester Present | `3E 00` → `7E 00` |
| Suppressed positive response | `3E 80` |
| Session-maintenance model | Configurable illustrative inactivity timer |
| Automatic Tester Present | Periodic `3E 80` transmission |
| Session fallback | Return to Default Session in the demo model |
| Diagnostic trace | Color-coded client, server, and state events |
| Adaptive AUTOSAR | Simplified diagnostic service-handling path |

---

## 🔁 UDS Message Examples

### Enter Programming Session

CLIENT → SERVER  10 02
SERVER → CLIENT  50 02

### Tester Present with Positive Response

CLIENT → SERVER  3E 00
SERVER → CLIENT  7E 00

### Tester Present with Positive Response Suppressed

CLIENT → SERVER  3E 80

## 🧪 Try These Scenarios

## Scenario 1: Session fallback
1. Select Send 10 02.
2. Observe entry into Programming Session.
3. Do not send additional diagnostic requests.
4. Observe the illustrative inactivity condition.
5. The simulator returns to Default Session.

## Scenario 2: Maintain the session
1. Select Send 10 02.
2. Send 3E 00 or 3E 80 before the demonstration timer expires.
3. Observe the session-maintenance behavior.
4. Compare the diagnostic traces for 3E 00 and 3E 80.

## Scenario 3: Automatic Tester Present
1. Enter Programming or Extended Diagnostic Session.
2. Select Start auto 3E 80.
3. Observe periodic Tester Present transmission.
4. Compare the configured transmission interval with the illustrative inactivity window.

## 📏 Standards and Scope
This project is an educational model based on concepts from:

ISO 14229 Unified Diagnostic Services
AUTOSAR diagnostic architecture
Adaptive AUTOSAR diagnostic service handling

[!WARNING] Timeout values and internal session-management behavior are configurable demonstrations. They must not be interpreted as universal ISO 14229 or AUTOSAR requirements.

⚠️ Disclaimer
This simulator is intended for learning and technical illustration.

**It is not:**

A production diagnostic tester
A standards-conformance test tool
An ECU programming application
A substitute for an ECU-specific diagnostic specification

The application does not establish communication with real vehicle networks or ECUs.


If this project helps with learning UDS diagnostics, consider giving the repository a ⭐
