# Kill chain attack flow chart
```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Identify input fields vulnerable to XSS| Weaponization[Weaponization]
    
    Weaponization -->|Craft malicious JavaScript payload| Delivery[Delivery]
    
    Delivery -->|Inject script into input fields e.g., product reviews| Exploitation[Exploitation]
    
    Exploitation -->|Victim loads compromised page| Installation[Installation]
    
    Installation -->|Steal session cookies or sensitive information| Command_Control[Command and Control]
    
    Command_Control -->|Exfiltrate session cookies or payment data to C&C server| Actions_Objectives[Actions on Objectives]
    
    Actions_Objectives -->|Make unauthorized purchases or perform account takeovers| Actions_Objectives
    Actions_Objectives -->|Redirect users to phishing websites| Actions_Objectives

