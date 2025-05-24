
# ✅ Server-Side GTM Container Audit Summary for Dan Belsky

**Container ID:** `GTM-M7BMM8ZQ`  
**Container Name:** Server Container SFZC  
**Discovered By:** SFZC WebOps (Greg Bilke)  
**Confirmed By Export:** Yes (Version 2, 2025-05-17)

---

## 🔍 Key Findings

- **Tag Present:** Facebook Conversions API (CAPI)  
- **Pixel ID Used:** `1062378757459509` (same as Web GTM container)
- **Trigger Type:** `ALWAYS` — fires on **all incoming events**
- **Consent Status:** `NOT_SET` — **no consent enforcement in place**
- **Access Level:** View-only for SFZC — cannot pause, edit, or disable
- **Maintainer:** Last edited by `belen.molinari@templeadv.com`

---

## ⚠️ Risks

| Risk                         | Details                                                                 |
|------------------------------|-------------------------------------------------------------------------|
| ❌ Consent not enforced       | GDPR/CCPA violation: CAPI events may be sent without user opt-in        |
| ⚠️ Duplicate tracking         | Shares Pixel ID with Web container — likely causing event duplication   |
| ⚠️ No current owner           | View-only access, undocumented until recent audit                       |
| ⚠️ Legal exposure             | No audit trail or consent logic to justify current behavior             |

---

## ✅ Current Status

- Awaiting reply from Belen (Temple) to determine if it is needed
- Export confirmed that **if active**, it is non-compliant
- Recommendation: prepare fallback decommission steps if no reply is received

---

## 📎 Reference Export

- **File:** `GTM-M7BMM8ZQ_v2.json`
- **Export Date:** 2025-05-17
- Available on request or in project Git repository

