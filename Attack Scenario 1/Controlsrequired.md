# Controls required using the STRIDE Model
```mermaid

graph TD
    %% STRIDE Threat Model

    %% Application Flow
    subgraph Web_Application
        A[User] -->|Requests Access| B[Web Server]
        B -->|Access Database| C[Database Server]
        B -->|Execute Logic| D[Business Logic]
        A -.->|Attempts to Access Admin Panel| E[Admin Interface]
        E -.->|Input Validation| F[Input Validation Layer]
    end

    %% Threats
    T1([Spoofing: Phishing Attack]) -.-> A
    T2([Tampering: SQL Injection]) -.-> C
    T3([Repudiation: Log Manipulation]) -.-> B
    T4([Information Disclosure: Sensitive Data Leak]) -.-> C
    T5([Denial of Service: XSS Attack]) -.-> B
    T6([Elevation of Privilege: XSS to Access Admin]) -.-> E

    %% Controls
    C1([Mitigation: Strong Authentication such as MFA]) --> T1
    C2([Mitigation: Input Validation & Parameterized Queries]) --> T2
    C3([Mitigation: Secure Logging & Monitoring]) --> T3
    C4([Mitigation: Encryption for Sensitive Data]) --> T4
    C5([Mitigation: Rate Limiting & Input Validation]) --> T5
    C6([Mitigation: Access Controls & Input Validation]) --> T6

    %% Connecting Threats to Controls
    T1 --> C1
    T2 --> C2
    T3 --> C3
    T4 --> C4
    T5 --> C5
    T6 --> C6
