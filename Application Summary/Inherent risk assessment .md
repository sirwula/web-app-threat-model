## Inherent risk assesment

An inherent risk assessment for our web app threat model, using the 3 attack scenarios of phishing emails, SQL injection, and XSS.

| Category          | Description                                             | Likelihood | Impact | Risk Rating | Scenario                                                   |
|-------------------|---------------------------------------------------------|------------|--------|-------------|-------------------------------------------------------------|
| Credentials       | Admin credentials stolen via phishing attack            | High       | High   | Critical    | Unauthorized access to backend, sensitive data compromised   |
| User Data         | User PII exposed due to SQL injection                   | Medium     | High   | High        | User information stolen, potential regulatory fines          |
| Application Data  | Application functionality disrupted by SQL injection    | Medium     | High   | High        | Application behavior altered, database integrity compromised |
| Session Data      | User sessions hijacked via XSS attack                   | High       | Medium | High        | Unauthorized user actions, potential impersonation           |
| Sensitive Data    | Financial and personal details exposed via XSS          | Medium     | High   | High        | Theft of sensitive user data                                |
| Third-Party Service | External service compromise due to phishing or SQLi   | Medium     | Medium | Medium      | Compromise of external service credentials                   |
| System Integrity  | System access by unauthorized users via phishing        | High       | High   | Critical    | System-wide integrity breach, admin functions compromised    |
