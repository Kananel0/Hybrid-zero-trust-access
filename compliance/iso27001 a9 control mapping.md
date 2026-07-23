# ISO 27001:2013 Annex A.9 Access Control Mapping

This document maps the technical controls configured within Microsoft Entra ID and Active Directory Domain Services (AD DS) to the required controls under ISO 27001:2013 Annex A.9.

---

## Control Mapping Matrix

| ISO 27001 Control | Requirement Summary | Implemented Technical Control | Verification / Evidence File |
|---|---|---|---|
| **A.9.1.1** Access Control Policy | Formal business requirements for access control must be documented. | Layered Conditional Access policies based on user risk, sign-in risk, device compliance, and location. | `policies/conditional-access-policy-matrix.md` |
| **A.9.1.2** Access to Networks and Network Services | Users shall only be provided access to specific network services they are authorized to use. | Named Locations blocking foreign/untrusted IP ranges; Microsoft Entra Private Access / Application Proxy. | `policies/named-locations-config.md` |
| **A.9.2.1** User Registration and De-registration | Formal process for assigning and revoking access. | Lifecycle Workflows and SCIM provisioning synced via Entra Connect from AD DS. | Entra Connect Sync Logs & Lifecycle Rules |
| **A.9.2.2** User Access Provisioning | Formal access provisioning process for all user types and roles. | Dynamic Security Groups and entitlement management packages for role-based access (RBAC). | Group Membership & Assignment Rules |
| **A.9.2.3** Management of Privileged Access Rights | Allocation and use of privileged access rights shall be restricted and controlled. | Privileged Identity Management (PIM) requiring Just-In-Time (JIT) activation, ticket numbers, and approvals. | `policies/pim-role-settings.md` |
| **A.9.2.6** Removal or Adjustment of Access Rights | User access rights shall be reviewed at regular intervals. | Quarterly Entra ID Access Reviews enforced for all Guest users and Privileged Roles. | Access Review Audit History Logs |
| **A.9.4.2** Secure Log-on Procedures | Access to systems and applications shall be controlled by a secure log-on procedure. | Enforced Phishing-Resistant MFA / Passwordless (FIDO2 / Authenticator) via Conditional Access. | Entra ID Authentication Methods Policy |