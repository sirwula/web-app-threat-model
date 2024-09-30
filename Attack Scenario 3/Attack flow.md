# Attack flow chart
```mermaid
flowchart LR
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px

    A[Reconnaissance] -->|Identify vulnerable input fields| B[Weaponization]
    B -->|Craft malicious JavaScript payload| C[Delivery]
    C -->|Inject script into user input fields| D[Exploitation]
    D -->|Victim loads compromised web page| E[Installation]
    E -->|Steal session tokens or sensitive data| F[Actions on Objectives]
    F -->|Impersonate users or exfiltrate data| G[Data Exfiltration]
    F -->|Tamper with health records| H[Data Manipulation]
    F -->|Redirect users to phishing sites| I[Service Disruption]
