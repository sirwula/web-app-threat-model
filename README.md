# web-app-threat-model
Threat modelling project for a web application using Kill Chain, STRIDE, and MITRE ATT&amp;CK methodologies.
System description included
Risk assesment and mitigation included

# Threat Modelling Workshop Summary
## Introduction
A 3 Hour threat modelling workshop took place to detail the runbook scenario of three attacks against the web-facing ecommerce application .

## Attendess
WEb application Eng team, Product Managers, DevEx Engineers and the DevSecOps Team.

## Scope
3 Scenarios were run covering: (1) AI Generated External phishing email utilising admin credentials, (2) Script-Based XSS (Cross-Site Scripting) Attack with Session Hijacking (3) Automated SQL Injection Targeting Privileged Database Queries.

## Methodology
All scenarios were run against the cyber attack killchain, utilising the Mitre Att&ack framework and STRIDE for control gap assessments. Culminating in identified risks.

## Conclusion
A total of 4 high risks and 1 medium risks were found during the threat modelling workshop.

## Controls Required
Regular security audits using ASVS specifically targeting the ecommerce web application to detect vulnerabilities and weaknesses in its security measures.
Patch management to ensure the ecommerce web application and its underlying technologies are up-to-date and protected against known vulnerabilities.
Comprehensive employee training on phishing awareness to educate users of the ecommerce web application about the risks of phishing attacks and how to identify and report suspicious emails.
Implementation of a Web Application Firewall (WAF) tailored to the ecommerce web application's traffic to monitor and filter incoming requests for malicious activity.
Deployment of Multi-factor Authentication (MFA) to enhance authentication security and prevent unauthorized access to the ecommerce web application.
Continuous network traffic monitoring to detect and respond to suspicious activity within the e commerce web application's infrastructure.
Implementation of Role-based Access Control (RBAC) within the ecommerce web application to limit access to sensitive financial data and functionalities based on user roles and permissions.


# Web-app threat Modelling Process Summary

```mermaid
mindmap
  root((Attack Begins))
    STRIDE/MITRE ATT&CK/Kill Chain
      Conduct Inherent Risk Assesment
      ::icon(fa fa-book)
      Create Critical Asset List
        Schedule and Scope Threat Modelling Workshop
    Controls Required
      Risks<br/>Mitigations
      Risk Summary
        Redmeiation workflow
            Slack
            JIRA 
    Attack Scenarios
      Attack 1
      Attack 2
      Attack 3
      