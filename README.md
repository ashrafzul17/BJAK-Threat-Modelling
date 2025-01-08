# BJAK-Threat-Modelling
# Threat Modelling Workshop Summary

## Introduction
A 3-hour threat modelling workshop was conducted to detail potential cyber attack scenarios targeting BJAK, Malaysia's leading insurance comparison platform. This exercise aimed to identify security gaps, assess risks, and recommend mitigations.

## Attendees
BJAK engineering team, Product Managers, DevOps Engineers, and the DevSecOps Team.

## Scope
5 scenarios were run covering:

1. Account takeover via credential stuffing attacks.
2. API abuse to manipulate insurance quotes and prices.
3. Sensitive data exposure due to insufficient encryption.
4. Business logic abuse in the insurance comparison process.
5. Supply chain attack targeting third-party service providers.

## Methodology
All scenarios were analyzed using the cyber attack kill chain, Mitre ATT&CK framework, and the STRIDE methodology for control gap assessments. This culminated in the identification of critical risks and gaps requiring immediate attention.

## Conclusion
A total of 3 high-risk scenarios, 2 medium-risk scenarios, and no low-risk scenarios were identified during the threat modelling workshop.

## Controls Required
1. Enforcement of multi-factor authentication (MFA) across all user accounts.
2. Regular API security audits to identify vulnerabilities and enforce strict access controls and rate limits.
3. End-to-end encryption for all data transmissions between BJAK’s platform, users, and third-party providers.
4. Implementation of input validation and logic validation to harden the business workflow against abuse.
5. Third-party risk management framework to assess and monitor vendors for security compliance.
6. Role-based access control (RBAC) to minimize unauthorized access to sensitive data or processes.
7. Incident response procedures to detect and respond to credential stuffing and other automated attacks in real time.
8. Use of an anomaly detection system to identify suspicious activities in the platform.

# Threat Modelling Process Summary

```mermaid

mindmap
  root((Attack Begins))
    STRIDE/MITRE ATT&CK/Kill Chain
      Conduct Inherent Risk Assessment
      ::icon(fa fa-book)
      Create Critical Asset List
        Schedule and Scope Threat Modelling Workshop
    Controls Required
      Risks and Mitigations
      Risk Summary
        Remediation Workflow
          Slack
          JIRA
    Attack Scenarios
      Account Takeover
      API Abuse
      Data Exposure
      Business Logic Abuse
      Supply Chain Attack


