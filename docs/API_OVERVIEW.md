# API Overview (Proposed)

This is a planning document. These endpoints do not exist until implemented and tested.

| Method | Proposed route | Purpose |
|---|---|---|
| POST | /api/v1/auth/register | Create owner account |
| POST | /api/v1/auth/login | Authenticate owner |
| POST | /api/v1/devices | Register an authorized device |
| GET | /api/v1/devices | List devices owned by current user |
| GET | /api/v1/devices/{deviceId}/status | Read permitted status |
| PUT | /api/v1/devices/{deviceId}/consent | Update optional sharing choices |
| POST | /api/v1/devices/{deviceId}/events | Submit permitted event summary |
| GET | /api/v1/alerts | List current owner's alerts |
| PATCH | /api/v1/alerts/{alertId} | Mark alert reviewed |
| DELETE | /api/v1/devices/{deviceId} | Remove device association |
| DELETE | /api/v1/account | Request account/data deletion |

## API Rules
- Require authentication except for explicitly public health checks and registration/login.
- Verify that the authenticated user owns the requested device.
- Enforce consent server-side, not only in the Android UI.
- Validate payloads and apply rate limits.
- Never return another user's device, alert, or location records.