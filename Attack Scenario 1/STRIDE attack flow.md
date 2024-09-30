# STRIDE flow chart

# Attack Description

The attacker is a black hat hacker who has conducted advanced research on our ecommerce web application. The attacker initiates the attack by identifying key personnel who likely had admin credentials to production environments. This way the attacker does not need to bypass a WAF or any other security controls but will instead have direct access to the environments as an admin.

# Methodology
The attack sequence below utilises the STRIDE framework along with the commonly used techniques. 

```mermaid
flowchart TD
    style Spoofing fill:#F4D03F,stroke:#000,stroke-width:2px
    style Tampering fill:#F5B041,stroke:#000,stroke-width:2px
    style Repudiation fill:#EB984E,stroke:#000,stroke-width:2px
    style Information_Disclosure fill:#E59866,stroke:#000,stroke-width:2px
    style Denial_of_Service fill:#DC7633,stroke:#000,stroke-width:2px
    style Elevation_of_Privilege fill:#BA4A00,stroke:#000,stroke-width:2px

    %% Attack Stages
    Spoofing[Spoofing: Phishing email to spoof admin identity] --> Tampering[Tampering: SQL Injection to alter database]
    Tampering[Tampering] --> Repudiation[Repudiation: Deny malicious activity by deleting logs]
    Repudiation[Repudiation] --> Information_Disclosure[Information Disclosure: Access sensitive data through SQL Injection]
    Information_Disclosure[Information Disclosure] --> Denial_of_Service[Denial of Service: Overload web server using XSS]
    Denial_of_Service[Denial of Service] --> Elevation_of_Privilege[Elevation of Privilege: Gain unauthorized admin access via XSS]

    %% Threat Scenarios in Detail
    subgraph Threat_Scenarios
        Spoofing -->|Phishing email with malicious link| Tampering
        Tampering -->|Inject malicious SQL query| Information_Disclosure
        Information_Disclosure -->|Extract sensitive data from database| Denial_of_Service
        Denial_of_Service -->|Inject XSS attack payload| Elevation_of_Privilege
        Elevation_of_Privilege -->|Gain full control over web application| Elevation_of_Privilege
    end
