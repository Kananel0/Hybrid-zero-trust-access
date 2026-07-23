# Conditional Access Policy Matrix

All policies follow the **[State] - [Target Users] - [Target App] - [Control]** naming convention and operate under a Zero Trust "Explicit Verification" model.

---

## Enforced Policy Rules

| Policy Name | Target Users / Groups | Target Apps | Conditions (Signals) | Access Control (Grants/Blocks) |
|---|---|---|---|---|
| `[ENFORCE] All Users - Require MFA` | All Users (Excl. Break-Glass) | All Cloud Apps | Any Location, Any Device | **Require MFA** |
| `[ENFORCE] Admins - Require Phishing-Resistant MFA` | Global Admins, Privileged Role Admins | All Cloud Apps | Any Location | **Require FIDO2 / Certificate-Based Auth** |
| `[ENFORCE] All Users - Block High Risk Sign-Ins` | All Users | All Cloud Apps | Sign-In Risk = High | **Block Access** |
| `[ENFORCE] All Users - Require Password Reset on User Risk` | All Users | All Cloud Apps | User Risk = High | **Require Self-Service Password Reset + MFA** |
| `[ENFORCE] Sensitive Apps - Require Compliant Device` | Finance, HR, IT Groups | Azure Portal, Workday, Salesforce | Unmanaged / Non-Compliant Device | **Require Hybrid AD Joined or Intune Compliant Device** |
| `[ENFORCE] Geo-Block - Untrusted Locations` | All Users | All Cloud Apps | Location = `Untrusted-Countries-Named-Location` | **Block Access** |

---

> **Note on Exclusions:** Emergency Break-Glass Accounts (`bg-admin-01@domain.com`) are explicitly excluded from Conditional Access MFA policies to prevent lockout scenarios, but are heavily monitored via Azure Monitor/Sentinel alerts.