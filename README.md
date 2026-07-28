# hybrid zero trust access

# Hybrid Enterprise Zero Trust Access Framework
### Microsoft Entra ID | Active Directory | Conditional Access | PIM | ISO 27001

![Status](https://img.shields.io/badge/status-complete-brightgreen)
![Platform](https://img.shields.io/badge/platform-Microsoft%20Entra%20ID-blue)
![Compliance](https://img.shields.io/badge/ISO%2027001-Annex%20A.9-orange)



---

## 📌 What This Project Is

This project simulates the identity and access architecture of a 3,000+ employee multinational enterprise running **hybrid identity** — on-premises Active Directory synced to Microsoft Entra ID via Entra Connect, supporting a global, partly-remote workforce across multiple regions.

It builds a full **Zero Trust access model** on top of that hybrid identity foundation, including:

- Hybrid identity synchronization (AD DS → Microsoft Entra Connect → Entra ID) using password hash sync and seamless SSO
- Layered **Conditional Access policies** driven by user risk, sign-in risk, device compliance, and application sensitivity
- **Named Locations** to distinguish trusted corporate IP ranges from untrusted/foreign geographies, enforcing MFA or blocking access outside them
- **Privileged Identity Management (PIM)** for just-in-time, time-bound, approval-based admin access  no standing privileged accounts
- **Access Reviews** for guest accounts and privileged roles, run on a recurring quarterly cycle
- Direct mapping of every control to **ISO 27001 Annex A.9 — Access Control**

## 🎯 Why I Built This

Most identity labs stop at "turn on MFA." Real enterprises don't run on a single control — they run on **layered, auditable, risk-based access decisions** that have to survive a compliance audit and a security incident at the same time.

I built this project to demonstrate that I can:
- Design identity architecture for a hybrid (not just cloud-native) environment, which is what most large enterprises actually run
- Translate business risk (a login from an unexpected country, an unmanaged device, a standing admin account) into concrete, enforceable policy
- Speak the language of both IT security teams and compliance/audit teams by tying technical controls to a recognized framework (ISO 27001)

## 🛡️ How This Protects the Organization

| Risk | Control Implemented | Outcome |
|---|---|---|
| Stolen credentials used from outside the corporate network | Named Locations + Conditional Access | Access is blocked or forced into step-up MFA outside trusted geographies |
| Compromised or unmanaged devices accessing sensitive apps | Device compliance based Conditional Access | Only Intune-compliant, corporate-managed devices reach sensitive resources |
| Standing admin accounts as a persistent attack target | PIM just-in-time elevation | Admin rights exist only for the duration needed, with approval and logging |
| Access sprawl — guests and privileged users keeping access they no longer need | Quarterly Access Reviews | Stale and unnecessary access is systematically removed, not left to chance |
| Failing an ISO 27001 audit due to undocumented access control | Full control-to-clause mapping | Every technical control has a corresponding, evidenced compliance clause |

## 🏗️ Architecture

```
On-Prem Active Directory
        │
        ▼
Microsoft Entra Connect (Password Hash Sync + Seamless SSO)
        │
        ▼
Microsoft Entra ID (Cloud Identity)
        │
        ├── Conditional Access (Risk + Device + Location signals)
        ├── Named Locations (Trusted/Untrusted geo & IP ranges)
        ├── PIM (Just-in-time privileged roles)
        └── Access Reviews (Guest + Privileged role recertification)
```

*(Full diagram: see `/architecture/hybrid-zero-trust-diagram.png`)*

## 📂 Repository Structure

```
├── architecture/
│   └── hybrid-zero-trust-diagram.png
├── policies/
│   ├── conditional access policy matrix.md
│   ├── named locations config.md
│   └── pim role settings.md
├── compliance/
│   └── iso27001-a9-control-mapping.md
├── screenshots/
└── README.md
```

## 🧰 Skills Demonstrated

`Microsoft Entra ID` · `Active Directory` · `Entra Connect` · `Conditional Access` · `Named Locations` · `PIM` · `Access Reviews` · `Zero Trust Architecture` · `ISO 27001 Annex A.9`

## 🔗 Related Certification

This project was built as part of my preparation for **Microsoft SC-300: Identity and Access Administrator**.


📩 Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/kananelo-mohale) if you'd like to discuss the design decisions behind this project.
