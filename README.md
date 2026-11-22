# PROJECT SHIELD
### AI-Assisted Anti-Theft Awareness & Mobile Recovery Support System

![Status](https://img.shields.io/badge/status-planning-blue) ![Platform](https://img.shields.io/badge/platform-Android-green) ![Focus](https://img.shields.io/badge/focus-privacy%20%26%20security-purple)

## Overview
Project SHIELD is a proposed Android application and backend that helps a device owner review permitted security events, receive understandable alerts, and follow safe recovery steps if a phone is missing. It is an educational prototype, not a guaranteed phone-recovery or law-enforcement tool.

## Problem Statement
When a phone is misplaced or stolen, the owner may not know the last location voluntarily shared by the device, whether a relevant security event was reported, or which safe next steps to take. SHIELD explores a single, privacy-conscious dashboard for registered owners.

## Aim
To design and demonstrate a consent-based mobile security support system combining owner/device registration, optional permitted status reporting, advisory event analysis, notifications, and recovery guidance.

## Objectives
- Secure owner registration, sign-in, and session handling.
- Register and manage only devices the signed-in user owns or is authorized to manage.
- Explain optional permissions and allow refusal or revocation.
- Process only supported information knowingly enabled by the owner.
- Analyze approved test/consented event summaries and explain advisory alerts.
- Display alerts and, when explicitly enabled, the last shared location with its timestamp.
- Provide a safe recovery checklist and links to official platform/carrier services.
- Document authorization, privacy controls, testing, and limitations.

## How It Works
1. Owner creates an account and signs in.
2. Owner registers an authorized device.
3. The app explains optional permissions; the owner may accept, decline, or revoke them.
4. The app sends only enabled, supported status/event summaries over HTTPS.
5. The backend checks identity, device ownership, and consent.
6. A rules-based analyzer (and later an optional evaluated ML model) creates advisory alerts.
7. The alert service notifies the registered owner.
8. The dashboard shows alerts and any available last-shared location with freshness information.
9. The app presents safe recovery guidance, including official device-finding tools, account security, carrier contact, and appropriate local authorities.

## Main Modules
| Module | Responsibility |
|---|---|
| Authentication | Owner registration, login, logout, session handling |
| Device Registration | Associate an authorized device with its owner |
| Permission & Consent Manager | Explain, record, and revoke optional data sharing |
| Device Status/Event Monitor | Receive supported, permitted status summaries |
| Analysis Engine | Evaluate approved sample/consented events and explain signals |
| Alert Service | Store and deliver owner-facing notifications |
| Owner Dashboard | Show status, alerts, and last-update timestamps |
| Optional Location View | Display only explicitly shared location updates |
| Recovery Guidance | Provide safe next steps and official support links |
| Audit & Admin Monitoring | Record minimal security actions and service health without exposing private data |

## Proposed Technology
| Layer | Candidate technology | Purpose |
|---|---|---|
| Android app | Kotlin + Android SDK | Mobile UI and supported device features |
| Backend A | Firebase Authentication, Firestore, Cloud Functions | Faster student prototype |
| Backend B | Java Spring Boot + REST API | Custom backend |
| Database | Firestore (A) or PostgreSQL (B) | App data |
| Notifications | Firebase Cloud Messaging | Owner alerts |
| Analysis | Transparent rules first; optional Python ML later | Advisory event analysis |
| Version control | Git + GitHub | Collaboration and releases |

**Architecture decision:** choose Firebase or Spring Boot for the first implementation; they are alternative backend approaches. Start with tested rules before attempting ML. Do not claim AI functionality until a model has actually been implemented and evaluated.

## Repository Structure
```
project-shield/
├── README.md
├── LICENSE
├── .gitignore
├── docs/
│   ├── PROJECT_PROPOSAL.md
│   ├── SYSTEM_ARCHITECTURE.md
│   ├── PRIVACY_AND_SECURITY.md
│   ├── API_OVERVIEW.md
│   ├── TEST_PLAN.md
│   ├── ROADMAP.md
│   ├── FLOWCHART.md
│   └── USER_GUIDE.md
├── android-app/       # planned Android source
├── backend/           # planned Firebase or Spring Boot implementation
├── ai-analysis/       # optional analysis prototype
├── assets/diagrams/
└── .github/
```

## Privacy & Responsible Use
- No covert tracking or monitoring.
- Use only on devices the user owns or is explicitly authorized to manage.
- Location sharing must be opt-in, visible, purpose-limited, and easy to stop.
- Never bypass Android permission prompts, device protections, account security, or platform restrictions.
- Use least privilege, HTTPS, server-side authorization, secure secrets, and defined retention/deletion rules.
- Treat analysis as advisory; explain signals and acknowledge false positives.
- Never commit passwords, API keys, signing keys, service-account files, or personal location histories.

## Limitations
Android background execution and permissions vary by OS version and manufacturer. A device may be offline, powered off, damaged, or unable to provide a fresh update. Always show when data was last updated; never imply stale data is live. The app cannot guarantee theft detection, remote control, or recovery. Use official provider recovery services for supported device-finding actions.

## Flowchart
See [docs/FLOWCHART.md](docs/FLOWCHART.md) for the application workflow, system architecture flowchart, and key decision rules. GitHub renders the Mermaid diagrams directly.

## How to Work on This Project
See [docs/USER_GUIDE.md](docs/USER_GUIDE.md) for the complete step-by-step user journey, student team development phases, suggested demo sequence, and feature completion checklist.

## Development Roadmap
See [docs/ROADMAP.md](docs/ROADMAP.md). The first milestone is authentication, device registration, consent controls, and an owner dashboard. Event analysis and optional location follow after security tests.

## Documentation
- [Project Proposal](docs/PROJECT_PROPOSAL.md)
- [System Architecture](docs/SYSTEM_ARCHITECTURE.md)
- [Privacy & Security](docs/PRIVACY_AND_SECURITY.md)
- [Proposed API](docs/API_OVERVIEW.md)
- [Test Plan](docs/TEST_PLAN.md)
- [Development Roadmap](docs/ROADMAP.md)
- [Project Flowcharts](docs/FLOWCHART.md)
- [How to Work on the Project](docs/USER_GUIDE.md)

## Project Status
**Planning / documentation baseline.** Update this section as features are implemented and tested. Documentation does not mean the application or backend is already working.

## Disclaimer
Educational project only. Not a forensic product, law-enforcement tool, or guaranteed recovery service. Follow applicable laws and platform policies.