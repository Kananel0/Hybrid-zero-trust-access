# Privileged Identity Management (PIM) Configuration

To adhere to the principle of Least Privilege (ISO 27001 A.9.2.3), zero admin accounts maintain permanent standing access. All administrative privileges are activated Just-In-Time (JIT).

---

## Role Assignment Policy Summary

| Entra ID Role | Assignment Type | Max Activation Duration | Requirements for Activation | Approval Required? |
|---|---|---|---|---|
| **Global Administrator** | Eligible | **2 Hours** | • MFA Verification<br>• Justification Text<br>• Incident Ticket Number | **Yes** (Requires 1 of 2 Designated Approvers) |
| **Privileged Role Administrator** | Eligible | **4 Hours** | • MFA Verification<br>• Justification Text | **Yes** |
| **User Administrator** | Eligible | **8 Hours** | • MFA Verification<br>• Justification Text | **No** (Auto-approved, logged) |
| **Conditional Access Administrator** | Eligible | **4 Hours** | • MFA Verification<br>• Justification Text | **No** (Auto-approved, logged) |

---

## Security Governance & Alerts
* **Notification Settings:** Email alerts are sent to the Security Operations Center (SOC) alias whenever any Global Administrator role is activated.
* **Standing Access Alert:** Entra ID PIM triggers an alert if any user is directly assigned a permanent admin role outside of PIM.