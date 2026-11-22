# Privacy & Security Requirements

## Core Rule
The app may only manage a device the signed-in user owns or is explicitly authorized to manage. It must never provide covert monitoring or tracking.

## Consent
- Explain each optional data category before requesting access.
- Make optional permissions genuinely optional.
- Show current sharing status in the app.
- Provide an easy stop/revoke control.
- Record consent changes and timestamps.

## Data Minimization
- Collect only fields needed for a stated feature.
- Do not collect contacts, messages, photos, microphone, or camera data.
- Do not collect location unless the owner explicitly enables it.
- Display the time and freshness of any location update.
- Define retention periods and delete expired records.

## Security Controls
- HTTPS for network traffic.
- Secure authentication and session expiry.
- Server-side authorization on every device and alert request.
- Least-privilege database rules and service credentials.
- Rate limiting and security-event logging.
- No plaintext passwords, API keys, or service-account files in Git.
- Validate inputs and avoid sensitive details in logs.

## Responsible Alerts
- Label detections as advisory, not proof of theft.
- Explain the signal that triggered an alert.
- Allow the owner to dismiss or report a false alert.
- Do not automatically accuse a person or take consequential action.

## Safe Recovery
Direct the owner to official platform device-finding tools, account-security settings, their carrier, and appropriate local authorities. Do not attempt to bypass device locks or platform security.