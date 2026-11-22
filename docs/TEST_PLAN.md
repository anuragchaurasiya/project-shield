# Test Plan

## Functional Tests
- Register with valid details; reject invalid or duplicate account data.
- Sign in and sign out.
- Register a device for the current owner.
- Reject device requests from a different account.
- Decline optional permissions and confirm limited features still work.
- Revoke consent and confirm future optional updates stop.
- Submit a synthetic test event and verify the expected advisory alert.
- Display location only when a valid owner-enabled update exists.
- Show a clear stale/no-data state when no recent update exists.
- Mark an alert as reviewed.

## Security Tests
- Reject unauthenticated API requests.
- Confirm User A cannot read or modify User B's device or alerts.
- Confirm revoked consent prevents further processing of that data category.
- Confirm secrets are absent from source control and logs.
- Verify rate limits and input validation.

## Usability Tests
- Permission explanations are understandable.
- Alert reason and timestamp are visible.
- Recovery instructions do not promise guaranteed recovery.
- Consent settings and data-deletion instructions are easy to find.

## Test Evidence
Record date, app/backend version, test case, expected result, actual result, and pass/fail. Use synthetic test data; do not commit real personal location histories.