# MITRE ATT&CK flow chart

# Attack Description

The attacker is a black hat hacker who has conducted advanced research on our ecommerce web application. The attacker initiates the attack by identifying key personnel who likely had admin credentials to production environments. This way the attacker does not need to bypass a WAF or any other security controls but will instead have direct access to the environments as an admin.

# Methodology
The attack sequence below utilises the MITRE ATT&CK framework along with the commonly used techniques. 

```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Attacker identifies web app admin and users via LinkedIn or web searches| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Crafts phishing emails| Delivery[Delivery]
    Delivery[Delivery] -->|Deploy phishing emails with malicious links or attachments| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Users/admin click malicious links triggering SQL Injection/XSS| Installation[Installation]
    Installation[Installation] -->|Attacker gains access to backend and installs backdoor| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Establishes communication with C&C server for further attacks| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Steals sensitive data such as PII, session tokens| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Tamper with database or manipulate records SQL injection| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Delivery -->|T1566.001 - Phishing| MITRE
    Exploitation -->|T1190 - Exploit Public-Facing Application through SQLi/XSS| MITRE
    Exploitation -->|T1059.003 - Command and Scripting Interpreter| MITRE
    Installation -->|T1106 - Execution through API install backdoor| MITRE
    Command_Control -->|T1102 - Web Service for C&C| MITRE
    Command_Control -->|T1105 - Ingress Tool Transfer| MITRE
    Actions_Objectives -->|T1078 - Valid Accounts by compromised admin credentials| MITRE
    Actions_Objectives -->|T1565.001 - Data Manipulation by altering database records| MITRE
    end

