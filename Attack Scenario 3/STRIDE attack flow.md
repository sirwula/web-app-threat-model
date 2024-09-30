# STRIDE attack flow chart
```mermaid
flowchart TD
    style S Spoofing fill:#F4D03F,stroke:#000,stroke-width:2px
    style T Tampering fill:#F5B041,stroke:#000,stroke-width:2px
    style R Repudiation fill:#EB984E,stroke:#000,stroke-width:2px
    style I Information Disclosure fill:#E59866,stroke:#000,stroke-width:2px
    style D Denial of Service fill:#DC7633,stroke:#000,stroke-width:2px
    style E Elevation of Privilege fill:#BA4A00,stroke:#000,stroke-width:2px

    S[Spoofing] -->|Attacker injects malicious JavaScript to impersonate user sessions| T[Tampering]
    
    T -->|Modify web page or user data through script injection| R[Repudiation]
    
    R -->|Lack of logging enables attacker to deny responsibility| I[Information Disclosure]
    
    I -->|Steal sensitive data from users session cookies, personal data| D[Denial of Service]
    
    D -->|Attacker disrupts service by overloading resources or causing errors via script| E[Elevation of Privilege]
    
    E -->|Gain higher privileges by exploiting stolen session tokens or cookies| E


