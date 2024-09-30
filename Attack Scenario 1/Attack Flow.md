# This is an attacker's flow using mermaid
```mermaid
sequenceDiagram
    participant Attacker
    participant WebApp
    participant CnCServer
    participant BackendServer
    participant User
    participant Admin

    activate Attacker
    Attacker->>WebApp: Identify Web Application vulnerabilities
    WebApp->>Attacker: Application identified with potential vulnerabilities
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Craft exploit for SQLi/XSS vulnerabilities
    WebApp->>Attacker: Exploit crafted
    deactivate Attacker

    activate Attacker
    Attacker->>User: Deploy phishing campaign targeting admin/user
    User->>Admin: Phishing email sent mimicking admin
    activate Admin
    Admin->>WebApp: Clicks on malicious link/download attachment
    WebApp->>Admin: Malware downloaded or session hijacked via XSS
    deactivate Admin
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: SQL Injection/XSS exploits executed
    WebApp->>BackendServer: Exploits web server/database access
    BackendServer->>CnCServer: Communication established with C&C server
    CnCServer->>BackendServer: Commands issued to maintain persistence
    BackendServer->>CnCServer: Data exfiltrated or actions performed
    deactivate Attacker
