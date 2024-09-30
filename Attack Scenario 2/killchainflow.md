# SQL ATTACK FLOW USING KILL CHAIN CHART

```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Identify vulnerable input fields e.g., login forms, search fields| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Craft malicious SQL query| Delivery[Delivery]
    Delivery[Delivery] -->|Inject SQL query into vulnerable field| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Execute SQL Injection, gain access to database| Installation[Installation]
    Installation[Installation] -->|Establish persistence by creating backdoor accounts| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Communicate with C&C server to exfiltrate data| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Extract sensitive data from database| Actions_Objectives
    Actions_Objectives[Actions on Objectives] -->|Modify or delete data in the database| Actions_Objectives
