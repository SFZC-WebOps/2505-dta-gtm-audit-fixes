# 🧠 Project Memory: GTM Tracking Updates on SFZC.org  
**Filename:** `2505-dta-gtm-updates-troubleshooting.md`  
**Project Code:** 2505-DTA-GTM-UPDATES  
**Last Updated:** 2025-05-14  

---

## 🔍 Project Overview
This project combines and manages tracking diagnostics and tag implementations for SFZC.org. It unifies two previously parallel tasks:

- Microsoft Clarity Integration via GTM
- Classy Donation Tracking (GA4 Ecommerce Events)

All work is scoped within the existing Google Tag Manager (GTM) setup on [SFZC.org](https://sfzc.org), and includes testing, debugging, and implementation across GA4 and Clarity.

---

## 👤 Roles & Responsibilities

| Role                     | Name                     | Contact                     |
|--------------------------|--------------------------|-----------------------------|
| Lead Implementer         | Greg Bilke               | webcoordinator@sfzc.org     |
| Analytics Owner / Sponsor | Dan Belsky              | dan.belsky@sfzc.org         |
| External Support         | Zoey Brown (Community Boost) | zoey@communityboost.org |

---

## 🧭 Task Areas Under This Project

### 🟦 Task: Classy → GA4 Ecommerce Tracking  
**Former File:** `2505-gta-classy-gtm-memory.md`

#### ✅ Known Issues Addressed
- Replaced GA4 event param `amount` → `value`
- Removed duplicate GA4 Config tag

#### 🧪 Diagnostic Findings
- GA4 events blocked on both `sfzc.org` and Classy subdomain
- Four Facebook Conversions API (CAPI) tags suspected to conflict with GA4
- Disabling CAPI temporarily allowed GA4 `purchase` to fire

#### ❓ Open Questions
- Are FB CAPI tags still required? → *Pending Dan’s input*
- Who implemented the original server-side tagging logic?
- Broader GA4 tracking (beyond ecommerce) affected?

#### 📋 Next Steps
- [ ] Confirm FB CAPI tag requirement
- [ ] Temporarily pause CAPI tags to confirm GA4 flow
- [ ] Validate broader GA4 tracking events
- [ ] Review network/server logs for GA4 block patterns

---

### 🟩 Task: Microsoft Clarity Setup via GTM  
**Former File:** `2505-dta-Clarity-heatmaps-memory.md`

#### 🔧 Setup Requirements
- Clarity script to be installed via GTM (Custom HTML tag in `<head>`)
- Target: **All Pages**

#### 🧪 To-Do Checklist
- [ ] Get Clarity script from Dan
- [ ] Implement GTM tag
- [ ] Confirm tag location in `<head>` via GTM
- [ ] Use DevTools to verify request to `clarity.ms`
- [ ] Confirm Clarity dashboard captures traffic

#### 🔗 Project Links
- [Clarity Dashboard](https://clarity.microsoft.com/projects/view/rfyzkzgfcs/dashboard?date=Last%203%20days)
- [Clarity Setup](https://clarity.microsoft.com/projects/view/rfyzkzgfcs/settings#setup)

---

## 🧰 Shared Diagnostics & Tools

- **Browser DevTools**: Inspect tag firing and network requests
- **GTM Preview Mode**: Tag validation
- **Server Logs**: Review request blocks
- **Clarity Dashboard**: Confirm pageview/session replay
- **GA4 DebugView**: Track event data in real-time

---

## 📎 Historical Notes

The contents of the following documents are now fully integrated into this file as structured tasks:
- `2505-gta-classy-gtm-memory.md`
- `2505-dta-Clarity-heatmaps-memory.md`

This file is now the canonical project memory document.

---

## 📌 Change Log

| Date       | Update Summary                                      | By          |
|------------|------------------------------------------------------|--------------|
| 2025-05-14 | Initial merged memory created from two task threads | Greg Bilke   |
