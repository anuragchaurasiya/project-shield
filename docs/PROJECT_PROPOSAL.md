# Project Proposal — PROJECT SHIELD

## Title
**AI-Assisted Anti-Theft Awareness & Mobile Recovery Support System**

## Introduction
Project SHIELD is a proposed Android application with a supporting backend. It helps a legitimate device owner review permitted device-status information, receive security-related alerts, and follow safe recovery guidance when a phone is missing.

## Problem Statement
After losing a phone, an owner may lack a convenient place to review the last location the device voluntarily shared, relevant app alerts, and practical next steps. SHIELD explores a privacy-conscious dashboard for this purpose.

## Aim
Design and demonstrate a consent-based mobile security support prototype combining account/device registration, optional permitted status reporting, advisory event analysis, owner notifications, and recovery guidance.

## Objectives
- Secure owner registration and sign-in.
- Register a device to its authenticated owner.
- Explain optional permissions and record user choices.
- Receive only supported information enabled by the owner.
- Analyze test/consented events and generate explainable advisory alerts.
- Show alerts and last-shared location with freshness information.
- Provide a safe recovery checklist and official support links.
- Test authorization, privacy, and core user flows.

## Scope
**Included:** authentication, device registration, consent UI, test-event ingestion, rule-based analysis, notifications, owner dashboard, optional last-shared location, and recovery guidance.

**Excluded:** covert tracking, monitoring another person's device, bypassing Android protections, guaranteed theft detection/recovery, and unsupported remote-control features.

## Methodology
1. Gather functional and privacy requirements.
2. Design screens, data model, and API boundaries.
3. Implement authentication and owner/device authorization.
4. Build permission explanations and consent controls.
5. Implement test-event ingestion and transparent rules.
6. Add alert delivery and dashboard views.
7. Add optional location display only for owner-enabled updates.
8. Test authorization, revoked permissions, offline/stale data, and unauthorized access.
9. Document results and limitations.

## Expected Deliverables
- Android prototype.
- Backend service or Firebase configuration.
- Event-analysis prototype and synthetic test data.
- Architecture, flowchart, and project documentation.
- Test report and demonstration.
- GitHub repository with issues, version history, and setup instructions.

## Evaluation Criteria
- Can an owner register, sign in, and register their own device?
- Are optional permissions clearly explained?
- Does the backend reject unauthorized access?
- Are alerts understandable and labelled advisory?
- Is the last shared location timestamp visible?
- Does the app handle stale/missing data safely?
- Can the user revoke sharing and request deletion?
- Are tests and limitations documented?

## Conclusion
SHIELD demonstrates how mobile development, backend services, notifications, and explainable event analysis can be combined responsibly. Success is measured by reliable, tested, privacy-respecting functionality—not by a promise that every stolen phone can be recovered.