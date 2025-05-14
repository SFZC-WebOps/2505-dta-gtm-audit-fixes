# 🧠 Project Memory: Classy → GA4 Transaction Tracking via GTM  
**File**: `2505-gta-classy-gtm-memory.md`  
**Project Code**: 2505-GTA-Classy-GTM  
**Maintainer**: Greg Bilke (Web Systems Operations Manager)  
**Last Updated**: 2025-05-12

---

## 🔍 Overview
This project addresses issues with ecommerce tracking of Classy donation transactions in GA4 (Google Analytics 4), using GTM (Google Tag Manager). There are known conflicts involving legacy Facebook Conversions API (CAPI) tags, GA4 event parameters, and server-side blocking.

---

## ✅ Current Known Facts

### GA4 & GTM Integration
- Community Boost was previously engaged to assist with GA4 & Facebook Ads tracking via GTM.
- GTM tag for Classy donations originally used `amount` — **not recognized by GA4**.
  - ✅ Fixed: Now uses `value`, which GA4 recognizes for revenue reporting.
- Duplicate GA4 Configuration tag was removed from GTM.
- GA4 `purchase` events still failed to appear after these fixes.

### Diagnostic Findings
- GA4 event requests appear **blocked by server**, both on:
  - `sfzc.org` (primary domain)
  - Classy subdomain (donation pages)
- Blocking confirmed via browser console during test donations.

### Facebook CAPI Tags
- GTM contains **four Facebook Conversions API tags**.
- When CAPI tags were **paused temporarily**, GA4 events fired successfully.
- Community Boost suggested that the CAPI tags may conflict with GA4 tracking and advised removal or further testing.

---

## ❓ Open Questions (Owner: Greg Bilke unless noted)

| Question                                                                 | Status         | Notes                              |
|--------------------------------------------------------------------------|----------------|------------------------------------|
| Are the Facebook Conversions API tags still needed?                     | ❓ Unconfirmed  | Need input from Dan Belsky         |
| Who originally implemented the server-side FB/GTM tagging setup?        | ❓ Unknown      | Possibly internal or past vendor   |
| Do we have access to server logs or network settings?                   | ✅ Confirmed    | Greg (Web Admin) has access        |
| Is the issue limited to ecommerce tracking or broader GA4 events?       | ❓ Unclear      | Needs structured GA4 validation    |
| Should we pause FB tags to reestablish GA4 clarity and tracking first?  | ❓ Pending Dan  | May proceed if GA4 priority is confirmed |

---

## 🔧 Recommendations from Community Boost
- ✅ Switch GA4 parameter from `amount` → `value`
- ✅ Remove duplicate GA4 config tag
- 🧪 Temporarily pause Facebook CAPI tags to test GA4 purchase events
- 🛠️ If tags are still needed, implement a server-side workaround
- ⚠️ Broader issue affects `sfzc.org` and not just Classy; outside their engagement scope

---

## 📅 Next Steps
- [ ] Confirm whether FB Conversions API tags are required with Dan
- [ ] Temporarily pause FB tags to validate full GA4 purchase event flow
- [ ] Check whether other GA4 event types are impacted
- [ ] Review server logs for blocked GA4 requests (both domains)
- [ ] Identify original implementation party for FB CAPI/server-side logic
