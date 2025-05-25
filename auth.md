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

| Risk                 | Details                                                      |
| -------------------- | ------------------------------------------------------------ |
| ❌ No Consent Control | Sends data without consent settings (non-compliant with GDPR/CCPA) |
| ⚠️ Ownership Unknown  | No clear current owner or maintenance path                   |
| ⚠️ Redundant Tracking | Uses same FB Pixel ID as Web container (1062378757459509)    |
| ⚠️ No Audit Trail     | Not documented in SFZC workflows prior to 2025-05-17 discovery |

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



### ✅ Verified Local Testing Environment (2025-05-24)
- A controlled GTM validation environment was created using OrbStack + Docker on macOS.
- URL: `http://localhost:8080` served via NGINX container mapped to `/Volumes/webops-work/SITES/gtm-test`
- Used container: `GTM-TGH83XK` (Preview Mode only)
- Consent Mode validated via Tag Assistant (Consent tab):
  - `analytics_storage`: Denied by default
  - `ad_storage`: Denied
  - `security_storage`: Granted
- Confirmed that GTM tags honor consent gating
- No changes were published to production or Drupal



------



## 🚧 Outstanding Questions / To Be Verified

- Is the server-side GTM container actively in use (e.g., routed via DNS, App Engine, or GA4 forwarding)?
- Can administrative access to `GTM-M7BMM8ZQ` be obtained from Temple Advertising?
- Are any tags still relying on the deprecated UA (`UA-1720237-1`)?
- The following core compliance and tracking capabilities are **not yet implemented** and require remediation before further publishing (these gaps expose SFZC to privacy compliance risk (GDPR/CCPA) and limit analytics accuracy. Tasks have been filed and are staged for remediation per project timeline):
  - **Consent Enforcement:** All tags lack `consentSettings`; Cookiebot CMP is not currently gating behavior
  - **Clarity Tag Deployment:** Microsoft Clarity is not firing on all pages and is not consent-aware
  - **Cross-Domain Tracking:** GA4 tag lacks `linker_domains`, causing session continuity loss across `sfzc.org`, `give.sfzc.org`, and `forms.sfzc.org`


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
  - Delegated GTM setup to external vendors in the past (e.g., Temple Advertising)
  - Priorities include GA4 data integrity, fundraising tracking, and privacy compliance.

- **Legacy Contractor:** _Temple Advertising (belen.molinari@templeadv.com)_



------



## 🚫 Production Safeguard Policy

> **MANDATORY DIRECTIVE: No tag changes, publishing actions, or tracking implementations may be performed on production environments unless explicitly validated in a controlled test environment.**

This project operates under a **strict isolation principle**:

- ✅ **All GTM changes must be staged in test environments first**, with all of the following confirmed:
  - `/test-page` route on sfzc.org
  - OrbStack/Docker-based local testbed (`http://localhost:8080`)
  - GTM Preview mode with Consent Debugger, Omnibug, and GA4 DebugView
- 🚫 **Do not publish changes directly to production containers until successfully validated in a staging or preview environment, including:**
  - Consent settings (`consentSettings`) are verified
  - Tag firing behavior is validated on controlled pages
  - Tracking parameters appear correctly in GA4 DebugView and all changes have been **successfully tested in GTM Preview Mode**
- ✅ Always:
  - Export and save GTM container versions (`.json`) before changes
  - Use scoped triggers (e.g., `Page URL contains /test-page`) during testing
  - Log all validation results in the associated `task-*.md` file

------

> 🔒 **This policy ensures GDPR/CCPA compliance, data accuracy, and protects against unintended data leakage or broken analytics.**
>  Any violations must be reported and remediated immediately.



------



## 🏷️ Git Tag History

This section records versioned project milestones across all GTM implementation phases.

| Tag                                  | Description                                                  | Date       |
| ------------------------------------ | ------------------------------------------------------------ | ---------- |
| `v1.0-initialized`                   | Baseline: GTM project memory initialized with Clarity, Classy, Health Check | 2025-05-xx |
| `v1.1-audit-reorg`                   | Reorganized memory and audit documentation structure         | 2025-05-xx |
| `v1.2-task-modularization`           | Task system modularized for fix tracking                     | 2025-05-xx |
| `v1.3-testing-strategy-complete`     | Local GTM test environment validated; consent/debug setup done | 2025-05-24 |
| `git tag v1.4-prod-safeguard-policy` | Policy added to auth.md enforcing test-only GTM changes before production publish | 2025-05-25 |

 

---

## 🔄 Change Log

| Date       | Change                                                       | By              |
| ---------- | ------------------------------------------------------------ | --------------- |
| 2025-05-18 | Added `📌 Interaction Prompts and Workflow Signals` section to formalize assistant behavior | Assistant       |
| 2025-05-18 | Clarified that `auth.md` should only store canonical, high-level project truths | Assistant       |
| 2025-05-19 | Updated Risk Assessment table with consent and ownership risks; added stakeholder directives from Dan Belsky | Greg Bilke (GB) |
| 2025-05-23 | Claude cross-check issuance                                  | GB              |
| 2025-05-24 | Added `Verified Local Testing Environment`                   | GB              |
