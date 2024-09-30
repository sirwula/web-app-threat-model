# STRIDE Flow chart

```mermaid
flowchart TD
    style Spoofing fill:#F4D03F,stroke:#000,stroke-width:2px
    style Tampering fill:#F5B041,stroke:#000,stroke-width:2px
    style Repudiation fill:#EB984E,stroke:#000,stroke-width:2px
    style Information_Disclosure fill:#E59866,stroke:#000,stroke-width:2px
    style Denial_of_Service fill:#DC7633,stroke:#000,stroke-width:2px
    style Elevation_of_Privilege fill:#CA6F1E,stroke:#000,stroke-width:2px

    Spoofing[Spoofing] -->|SQL Injection allows impersonating users| Tampering[Tampering]
    Tampering[Tampering] -->|Manipulate database queries to modify data| Repudiation[Repudiation]
    Repudiation[Repudiation] -->|Lack of proper logging makes it hard to trace the attacker| Information_Disclosure[Information Disclosure]
    Information_Disclosure[Information Disclosure] -->|Access sensitive data via injected queries| Denial_of_Service[Denial of Service]
    Denial_of_Service[Denial of Service] -->|Disrupt database availability with destructive queries| Elevation_of_Privilege[Elevation of Privilege]
    Elevation_of_Privilege[Elevation of Privilege] -->|Gain admin-level access by exploiting vulnerabilities| Elevation_of_Privilege
