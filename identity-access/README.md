# azure-security-labs
Hands-on Azure security and governance labs aligned to enterprise cloud security practices.

# Identity and Access Management

## Objective
Implement secure identity and access controls using Microsoft Entra ID to support least-privilege access in Azure environments.

## Scope
This area focuses on core identity and access management concepts, including:
- User and group management
- Role-based access control (RBAC)
- Administrative role separation
- Conditional access concepts

## Approach
The labs in this section emphasize:
- Minimizing standing privileges
- Assigning access at the appropriate scope
- Understanding how identity controls reduce risk in regulated environments

## Notes
Content is added incrementally as labs are completed and refined.

## 02/03/2026
Microsoft Cloud Security Benchmark — Identity & Privileged Access (Condensed Summary)
Unit: Identity Management & Privileged Access (IM‑1 through IM‑7)
Overall Theme
The benchmark lays out identity‑centric security controls that apply across all cloud platforms.
Every section follows the same pattern:

Security principle
Azure guidance
AWS guidance
GCP guidance

Across all three platforms, the repeated message is:
Centralize identity, enforce strong authentication, minimize privilege, automate identity lifecycle, and validate access conditions.

IM‑1: Centralize Identity & Authentication
Core idea: Use a single, centralized identity provider for all cloud and on‑prem resources.
Azure: Standardize on Microsoft Entra ID; avoid local accounts.
AWS: Use AWS IAM or federate AWS to Entra ID via SSO.
GCP: Use Google Cloud IAM or federate to Entra ID via SSO.

Why it matters: Reduces duplicate accounts, inconsistent policies, and unmanaged identities.

IM‑2: Protect Identity & Authentication Systems
Core idea: Treat identity systems as high‑value assets.
Common controls across platforms:

Restrict privileged roles
Require MFA for privileged access
Monitor and audit high‑risk activity
Follow least privilege
Use baselines and secure score–type tools
Azure: Entra ID Secure Score, Identity Protection, Defender for Identity.
AWS: IAM best practices, Access Advisor, credential reports.
GCP: Super admin best practices, IAM audit logs, Org Policy Service.

IM‑3: Use Managed Application Identities
Core idea: Applications should authenticate using managed identities, not human accounts or long‑lived secrets.
Azure: Managed Identities + service principals with certificates.
AWS: IAM Roles + service‑linked roles.
GCP: Google‑managed service accounts + Policy Intelligence.
Why it matters: Eliminates hard‑coded credentials and automates rotation.

IM‑4: Authenticate Servers & Services
Core idea: Always authenticate servers using TLS; verify certificates; use mutual TLS when needed.
All three platforms emphasize:
TLS enabled by default
Never disable TLS
Client apps must validate certificates

IM‑5: Use Single Sign‑On (SSO)
Core idea: Use SSO to reduce duplicate accounts and simplify user access.
Azure: Entra ID SSO for cloud + on‑prem apps.
AWS: AWS SSO + Cognito for customer‑facing apps.
GCP: Cloud Identity SSO for enterprise and external identities.

IM‑6: Enforce Strong Authentication (MFA / Passwordless)
Core idea: Password‑only authentication is legacy.
All platforms emphasize:
MFA for all users, especially admins
Passwordless where possible
Disable default credentials
Follow strong password policies if passwords must exist
Azure: Windows Hello, FIDO2, Authenticator app, Conditional Access MFA.
AWS: IAM MFA for all users.
GCP: MFA + Advanced Protection Program for super admins.

IM‑7: Conditional / Attribute‑Based Access
Core idea: Enforce access based on trusted signals (Zero Trust).
Signals include:
User risk
Device trust
Location
Group membership
Behavioral analytics
Azure: Conditional Access policies (MFA for admins, block legacy auth, risky sign‑ins, trusted locations).
AWS: IAM policy conditions, SCPs, permission boundaries.
GCP: IAM Conditions in role bindings.

The Big Picture (Ultra‑Condensed)
Across Azure, AWS, and GCP, the benchmark repeats the same seven identity pillars:
Centralize identity
Protect identity systems
Use managed identities
Authenticate servers with TLS
Use SSO
Enforce MFA/passwordless
Apply conditional access / attribute‑based access
The cloud‑specific sections differ only in naming and tooling — the principles are identical.
