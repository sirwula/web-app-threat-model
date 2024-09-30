MITRE AT&CK Flow chart
```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Initial_Access fill:#F5B041,stroke:#000,stroke-width:2px
    style Execution fill:#EB984E,stroke:#000,stroke-width:2px
    style Persistence fill:#E59866,stroke:#000,stroke-width:2px
    style Credential_Access fill:#DC7633,stroke:#000,stroke-width:2px
    style Collection fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Exfiltration fill:#BA4A00,stroke:#000,stroke-width:2px
    style Impact fill:#A93226,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance T1592]
    Reconnaissance -->|Identify vulnerable input fields| Initial_Access[Initial Access T1190]
    
    Initial_Access -->|Inject malicious script| Execution[Execution T1059.007]
    
    Execution -->|User loads malicious page| Persistence[Persistence T1136.001]
    
    Persistence -->|Steal session cookies| Credential_Access[Credential Access T1559.001]
    
    Credential_Access -->|Obtain session tokens| Collection[Collection T1005]
    
    Collection -->|Steal sensitive customer data| Exfiltration[Exfiltration T1041]
    
    Exfiltration -->|Send stolen data to C&C server| Impact[Impact T1485]
    Impact -->|Account takeover or unauthorized purchases| Impact
    Impact -->|Redirect users to phishing sites| Impact
