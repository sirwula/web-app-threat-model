# KILL CHAIN flow chart

# Attack Description

The attacker is a black hat hacker who has conducted advanced research on our ecommerce web application. The attacker initiates the attack by identifying key personnel who likely had admin credentials to production environments. This way the attacker does not need to bypass a WAF or any other security controls but will instead have direct access to the environments as an admin.

# Methodology
The attack sequence below utilises the KILL CHAIN ATT&CK framework along with the commonly used techniques. 

```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Identify admin users with Admin credentials| Weaponization[Weaponization]
    Weaponization[Weaponization] -->|Craft exploit targeting SQL Injection or XSS| Delivery[Delivery]
    Delivery[Delivery] -->|Send phishing email with malicious link| Exploitation[Exploitation]
    Exploitation[Exploitation] -->|Execute SQL Injection to access database| Installation[Installation]
    Installation[Installation] -->|Establish persistence via backdoor access| Command_Control[Command and Control]
    Command_Control[Command and Control] -->|Communicate with C&C server| Actions_Objectives[Actions on Objectives]
    Actions_Objectives[Actions on Objectives] -->|Steal sensitive data| Actions_Objectives
    Actions_Objectives[Actions on Objectives] -->|Tamper with application data through XSS| Actions_Objectives




