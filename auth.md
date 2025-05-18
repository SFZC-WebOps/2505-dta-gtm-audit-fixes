---
# 📂 2505-DTA-GTM Master Authority Document
> 📌 _This document serves as the single source of truth and authoritative record for the `2505-DTA-GTM` project, encompassing GTM container ownership, configuration integrity, and cross-account relationships._

---

## 🔐 GTM Container Ownership

### Primary Container: `sfzc.org`
- **GTM Container ID:** `GTM-TGH83XK`
- **GTM Account ID:** `2568135939`
- **Container Internal ID:** `8467147`
- **Environment:** Web
- **Source File:** `GTM-TGH83XK_v15.json`
- **Date Exported:** 2025-05-16 22:40:56 UTC
- **Container Name (UI):** `sfzc.org`

### Notes:
- This is the primary container managing GTM for the main SFZC web properties.
- The container contains **24 tags**, **19 triggers**, **98 variables**, **1 custom template**, and **14 built-in variables**.
- GA4 is used with Measurement ID `G-BRXZCXMZP5`.
- UA tracking ID `UA-1720237-1` is also present.
- Facebook Pixel ID `1062378757459509` is implemented.

---

## 🌐 Additional Containers Discovered

### Server-Side Container
- **GTM Container ID:** `GTM-M7BMM8ZQ`
- **Container Name (UI):** `Server Container SFZC`
- **Last Edited By:** belen.molinari@templeadv.com
- **Last Live Version:** `v2`
- **Access Level:** View-only for SFZC team
- **Primary Purpose:** Facebook Conversions API server-side forwarding

### Risk Assessment
| Risk                  | Details                                                                 |
|-----------------------|-------------------------------------------------------------------------|
| ❌ No Consent Control | Sends data without consent settings (non-compliant with GDPR/CCPA)     |
| ⚠️ Ownership Unknown  | No clear current owner or maintenance path                              |
| ⚠️ Redundant Tracking | Uses same FB Pixel ID as Web container (1062378757459509)               |
| ⚠️ No Audit Trail     | Not documented in SFZC workflows prior to 2025-05-17 discovery           |

---

## 📋 Verified Tracking IDs and Tags
| Platform            | ID / Name                      | Deployment Context              |
|---------------------|----------------------------------|----------------------------------|
| GA4                 | G-BRXZCXMZP5                    | Web (GTM-TGH83XK)               |
| Universal Analytics | UA-1720237-1                   | Web (GTM-TGH83XK)               |
| Facebook Pixel      | 1062378757459509               | Web + Server-Side (GTM-M7BMM8ZQ) |
| Microsoft Clarity   | rfyzkzgfcs                     | Web (Official script tag)       |
| Cookiebot CMP       | eb8e5eb5-b468-4382-a91f-f6678ac780a2 | CMP enforcement tag           |

---

## 🚧 Outstanding Questions / To Be Verified
- Is the server-side GTM container actively in use (e.g., routed via DNS, App Engine, or GA4 forwarding)?
- Can administrative access to `GTM-M7BMM8ZQ` be obtained from Temple Advertising?
- Are any tags still relying on the deprecated UA (`UA-1720237-1`)?

---

## 🕸️ Related Projects / Cross-Domain Tracking
- **Associated Domains (Needs linker):**
  - `give.sfzc.org`
  - `forms.sfzc.org`
  - `sfzc.org`

- **Linker Status:** GA4 Configuration tag currently **missing `linker_domains`** field.

---

## 🔄 Change Management
| Date       | Action / Discovery                                | Source                  |
|------------|----------------------------------------------------|-------------------------|
| 2025-05-16 | Exported GTM-TGH83XK v15 container for audit       | GTM UI                  |
| 2025-05-16 | Initial tag, trigger, consent, and tracking audit  | gtm-container-audit.md  |
| 2025-05-17 | Server container GTM-M7BMM8ZQ discovered, logged   | GTM UI + Chat review    |

---

## 🧭 Governance
- **SFZC WebOps Admin Contact:** _Greg Bilke (greg.bilke@sfzc.org)_
- **IT Director:** _Dan Belsky_
- **Legacy Contractor:** _Temple Advertising (belen.molinari@templeadv.com)_

---

> 📎 _This file should be updated anytime container ownership changes, access permissions are granted/revoked, or new containers are discovered._
