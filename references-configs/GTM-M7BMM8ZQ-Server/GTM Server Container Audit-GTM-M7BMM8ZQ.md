# 📦 GTM Server Container Audit: `GTM-M7BMM8ZQ`

**Container Name:** Server Container SFZC  
**Container ID:** GTM-M7BMM8ZQ  
**Type:** Server-Side GTM  
**Discovered:** 2025-05-17  
**Source File:** `GTM-M7BMM8ZQ_v2.json`  
**Last Edited By:** belen.molinari@templeadv.com  
**Live Version:** v2 (published 10 months ago)  
**Access Mode:** View-only (not owned by SFZC team)  

---

## 🔍 Summary

This server-side GTM container was discovered during the GTM tracking reset audit for SFZC.org. It is **not currently documented** in any of our workflows and appears to have been created and managed by a past external contractor (Temple Advertising).

### 🚨 Key Findings

- **Tag Present:** Facebook Conversions API (`Conversions API Tag`)
- **Trigger Type:** Fires on *all events* (`Always`)
- **Client Type:** GA4 Server Client (`gaaw_client`)
- **Consent:** ❌ **No consent gating** present (`consentStatus: NOT_SET`)
- **Redundancy Risk:** Uses the same Facebook Pixel ID (`1062378757459509`) as the Web GTM container
- **Audit Trail:** Last modified by Temple Advertising; no documentation or access known to current team
- **Tracking Method:** Designed to receive GA4 events and forward to Facebook via CAPI server-side

---

## ⚠️ Risk Assessment

| Risk Category | Status | Details |
|---------------|--------|---------|
| Consent Compliance | ❌ | No integration with Cookiebot or Consent Mode |
| Redundant Tracking | ⚠️ | May duplicate CAPI events already sent via `GTM-TGH83XK` (Web) |
| Data Ownership | ❌ | Not owned or editable by SFZC team |
| Privacy Exposure | ⚠️ | CAPI data may be sent server-side even if user declines tracking |
| DNS/CNAME Routing | ❓ | Unknown if DNS or GA4 traffic is routed through this container |

---

## ✅ Recommended Actions

- [ ] Determine if DNS or GA4 settings are routing events to `GTM-M7BMM8ZQ`
- [ ] Confirm with Dan Belsky whether Temple Advertising still manages this
- [ ] Archive or deactivate if not explicitly needed (to avoid duplicate CAPI traffic)
- [ ] If retained, enforce consent with Consent Mode + Cookiebot sync
- [ ] Add formal documentation and ownership structure if used long-term

---

## 📁 Related Files

- `GTM-M7BMM8ZQ_v2.json` — exported container version
- `docs/gtm-container-audit-GTM-TGH83XK-v15.md` — audit of main Web container
- `2505-dta-gtm-updates-troubleshooting-memory.md` — full memory record

---

_This file is part of the SFZC GTM tracking reset and compliance project (`2505-DTA-GTM-UPDATES`)._
