# Named Locations Configuration

Named Locations define trusted corporate network boundaries and risky geographic zones to drive real-time Conditional Access decisions.

---

## Configured Named Locations

### 1. Trusted Corporate Egress IPs (`Trusted-Corporate-HQ`)
* **Type:** IP Ranges (IPv4 / IPv6)
* **Marked as Trusted:** Yes
* **Purpose:** Allows bypass of strict device-compliance checks for internal on-premises maintenance while maintaining MFA requirements.
* **IP Ranges:**
  * `198.51.100.0/24` (HQ Primary Egress)
  * `203.0.113.50/32` (Data Center VPN Endpoint)

---

### 2. Untrusted Geographic Regions (`Blocked-HighRisk-Countries`)
* **Type:** Countries / Regions
* **Marked as Trusted:** No
* **Include Unknown Areas:** Yes
* **Purpose:** Feeds directly into the Geo-Block Conditional Access policy to drop connection attempts at the perimeter.
* **Targeted Regions:** Selected high-risk foreign countries outside of primary operating jurisdictions.