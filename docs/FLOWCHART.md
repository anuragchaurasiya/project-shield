# Project SHIELD — Flowchart

The diagrams below describe the proposed workflow. They are design diagrams, not proof that the app or backend has already been implemented.

## 1. Owner / application workflow

```mermaid
flowchart TD
    A([Start]) --> B[Open Project SHIELD]
    B --> C[Read purpose and privacy notice]
    C --> D{Already registered?}
    D -- No --> E[Create owner account]
    D -- Yes --> F[Sign in]
    E --> F
    F --> G[Register an owned or authorized device]
    G --> H[Explain optional permissions]
    H --> I{Owner gives consent?}
    I -- No --> J[Keep optional sharing disabled]
    I -- Yes --> K[Enable only selected supported sharing]
    J --> L[Open owner dashboard]
    K --> L
    L --> M[View device status and timestamps]
    M --> N{A test or permitted event arrives?}
    N -- No --> M
    N -- Yes --> O[Backend validates owner, device and consent]
    O --> P{Validation successful?}
    P -- No --> Q[Reject event and record minimal security log]
    P -- Yes --> R[Analyze event using transparent rules]
    R --> S[Create explainable advisory alert]
    S --> T[Notify registered owner]
    T --> U[Review alert and safe recovery checklist]
    U --> V[Use official recovery and account-security services]
    V --> W([End / Continue monitoring])
    Q --> M
    W --> M
```

## 2. High-level system architecture

```mermaid
flowchart LR
    A[Android App] -->|HTTPS, signed-in session| B[Backend API]
    B --> C[Authentication and authorization]
    B --> D[Consent and device registry]
    B --> E[Event validation]
    E --> F[Rules-based analysis]
    F --> G[Alert service]
    G -->|Owner notification| A
    B <--> H[(Database)]
    A --> I[Owner dashboard]
    I --> J[Safe recovery guidance]
```

## 3. Key decision rules
- If the owner declines optional permission, that data is not collected or uploaded.
- If the owner revokes consent, optional sharing stops.
- If the backend cannot verify account, device ownership, or consent, it rejects the event.
- Alerts are advisory and may be incorrect; the app must explain the reason and show data freshness.
- Location, if included later, is shown only when explicitly enabled by the authorized owner.
