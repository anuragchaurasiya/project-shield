# How to Work on Project SHIELD

This guide explains the intended user journey and a practical development workflow for the student team. The repository currently contains planning documentation; build and test each feature before marking it complete.

## A. How the application is intended to work

1. **Open the app:** The device owner sees the purpose, limitations, and privacy notice.
2. **Create an account / sign in:** The owner authenticates using the selected authentication provider.
3. **Register an authorized device:** The signed-in owner adds only a device they own or are authorized to manage.
4. **Review consent:** The app explains each optional permission and why it is needed. The owner can decline or revoke permission.
5. **Share permitted information:** Only supported data explicitly enabled by the owner is sent securely. The app must show when sharing is active.
6. **Backend validation:** The backend verifies the signed-in owner, device association, and consent before accepting data.
7. **Analyze an event:** The first version uses transparent, testable rules. Any later ML model must be evaluated and must explain that its result is advisory.
8. **Send an alert:** The owner receives a notification about the reported event.
9. **Review the dashboard:** The owner can view alerts, device status, and any optional last-shared location with its timestamp.
10. **Follow recovery guidance:** The app gives safe steps such as using official device-finding services, securing accounts, contacting the carrier, and contacting appropriate local authorities.

## B. How the student team should develop it

### Phase 1 — Prepare
- Read the [project proposal](PROJECT_PROPOSAL.md), [architecture](SYSTEM_ARCHITECTURE.md), and [privacy and security rules](PRIVACY_AND_SECURITY.md).
- Install Android Studio, a supported JDK, Git, and the Android SDK.
- Decide as a team whether the prototype will use **Firebase** or **Spring Boot**. They are alternative backend choices; do not build both at the beginning.
- Create a task board and assign UI, backend, testing, and documentation responsibilities.

### Phase 2 — Build the minimum working prototype
- Create the Android project and a simple welcome/sign-in screen.
- Add authentication using the selected backend.
- Add authorized-device registration.
- Build a consent and permission explanation screen with a clear off/revoke option.
- Build the owner dashboard using sample data first.
- Add secure backend endpoints and server-side ownership checks.

### Phase 3 — Add alerts safely
- Define a small set of harmless, simulated test events.
- Implement transparent rules and readable reasons for each alert.
- Add notifications to the registered owner.
- Show timestamps and distinguish current data from old data.
- Add optional location only after consent, visibility, and revocation are tested.

### Phase 4 — Test and demonstrate
- Follow the [test plan](TEST_PLAN.md).
- Test denied and revoked permissions, wrong-account access, offline devices, stale updates, and false alerts.
- Demonstrate with test accounts and simulated data—not another person's phone or private data.
- Record screenshots, test results, known limitations, and a short demo video if appropriate.

## C. Suggested demo sequence

1. Launch the app and explain the privacy notice.
2. Sign in with a test account.
3. Register a test device.
4. Show that optional sharing is off until the owner chooses to enable it.
5. Trigger a simulated event.
6. Show the advisory alert and its explanation.
7. Open the dashboard and point out the last-updated timestamp.
8. Show the safe recovery checklist.
9. Demonstrate how to turn off optional sharing or revoke permission.

## D. Definition of done for each feature

A feature is complete only when its UI, backend behavior (if applicable), authorization, error handling, tests, and documentation are in place. Never describe a planned screen, API, AI model, or location feature as implemented until it works and has been tested.

## Important safety rules
- Never track a person or device secretly.
- Never bypass operating-system permissions, account security, or device protections.
- Do not collect real location histories for a classroom demo; use simulated data.
- Do not promise that SHIELD can locate or recover every missing phone.
- Keep API keys, passwords, signing keys, and service credentials out of Git.
