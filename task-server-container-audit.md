---
# 📌 Task: Audit GTM Server Container (`GTM-M7BMM8ZQ`)
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Determine the current status and compliance of the server-side GTM container (`GTM-M7BMM8ZQ`), and decide whether to retain, reconfigure, or decommission it.

---

## 🔍 Problem Statement
- Container was implemented by Temple Advertising
- SFZC team has view-only access
- Contains Facebook Conversions API tag
- No consent settings are configured
- Container use is undocumented and potentially redundant

---

## 🛠️ Audit Summary

### ⚠️ Configuration Details
| Property           | Value                                  |
|--------------------|----------------------------------------|
| Container ID       | GTM-M7BMM8ZQ                           |
| Purpose            | Facebook CAPI via GA4 client           |
| Consent Config     | ❌ Not Set                             |
| Last Editor        | belen.molinari@templeadv.com           |
| Current Access     | View-only                              |
| Duplicate Tag      | FB Pixel ID `1062378757459509`         |

---

## 🛠️ Recommended Actions

### ✅ Step 1: Confirm Usage
- Check if GA4 or other tags are routed to the server container
- Use DNS settings, GTM client logs, or GA4 DebugView

### ✅ Step 2: Review Legal and Risk Implications
- Validate whether CAPI events are being sent without consent
- Assess GDPR/CCPA exposure if true

### ✅ Step 3: Contact Contractor or Disable
- Try to regain access from Temple Advertising
- If no access and non-critical, recommend disabling container

### ✅ Step 4: Enforce Consent If Retained
- Add conditional triggers based on granted consent
- Use server-side logic to mirror Cookiebot status

---

## 📋 Decision Checklist
- [ ] Confirmed if container is in active use
- [ ] GA4 or FB integration confirmed or rejected
- [ ] Access path or point-of-contact established
- [ ] Consent logic enforced or container disabled

---

## 🔄 Change Log
| Date       | Change                        | By         |
|------------|-------------------------------|------------|
| 2025-05-18 | Task doc created               | Assistant  |
