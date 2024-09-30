MITRE Att&ck flow chart

```mermaid
flowchart TD
    style Initial_Access fill:#F4D03F,stroke:#000,stroke-width:2px
    style Execution fill:#F5B041,stroke:#000,stroke-width:2px
    style Persistence fill:#EB984E,stroke:#000,stroke-width:2px
    style Privilege_Escalation fill:#E59866,stroke:#000,stroke-width:2px
    style Defense_Evasion fill:#DC7633,stroke:#000,stroke-width:2px
    style Credential_Access fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Discovery fill:#BA4A00,stroke:#000,stroke-width:2px
    style Collection fill:#A04000,stroke:#000,stroke-width:2px
    style Exfiltration fill:#8E2F00,stroke:#000,stroke-width:2px
    style Impact fill:#641E16,stroke:#000,stroke-width:2px

    Initial_Access[Initial Access T1190] -->|Find vulnerable input fields login/search| Execution[Execution]
    Execution[Execution T1059.007] -->|Execute SQL Injection payload| Persistence[Persistence]
    Persistence[Persistence T1078] -->|Create backdoor admin accounts| Privilege_Escalation[Privilege Escalation]
    Privilege_Escalation[Privilege Escalation T1078.003] -->|Use new admin access for higher privileges| Defense_Evasion[Defense Evasion]
    Defense_Evasion[Defense Evasion T1070.004] -->|Delete logs to hide activity| Credential_Access[Credential Access]
    Credential_Access[Credential Access T1078] -->|Steal admin credentials from DB| Discovery[Discovery]
    Discovery[Discovery T1217] -->|Map database structure and sensitive tables| Collection[Collection]
    Collection[Collection T1530] -->|Extract sensitive information| Exfiltration[Exfiltration]
    Exfiltration[Exfiltration T1041] -->|Transfer stolen data to external server| Impact[Impact]
    Impact[Impact T1485] -->|Modify or delete data in the database| Impact
