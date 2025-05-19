# 📝 GTM Audit & Compliance Project — Status Report for Dan Belsky  
**Prepared by:** Greg Bilke  
**Date:** 2025-05-20  

---

## 🎯 Project Purpose  
This project aims to:
- Restore visibility and control over all GTM tracking across SFZC sites  
- Retire deprecated Universal Analytics (UA) and migrate to GA4  
- Enforce GDPR/CCPA compliance using Cookiebot for consent gating  
- Audit undocumented GTM containers and identify any privacy or ownership risks  

---

## 🧾 Current State  
**Primary Container Audited:** `GTM-TGH83XK`  
**Audit Version:** `v15` (Exported 2025-05-16)  
**No changes have been made yet — tasks have been scoped but not implemented.**

---

## 🔍 Key Audit Findings (No Tasks Started Yet)

### 1. ❌ Consent Enforcement Missing
- 24 tags lack any `consentSettings`
- Cookiebot CMP exists but is not linked to tag behavior  
📄 `task-consent-enforcement.md`

### 2. ⚠️ Universal Analytics Still Active
- `UA-1720237-1` tags still present (deprecated July 2023)  
📄 `task-phase-out-ua.md`

### 3. ⚠️ Cross-Domain Tracking Gaps
- GA4 Configuration tag is missing `linker_domains` for `give.sfzc.org`, `forms.sfzc.org`  
📄 `task-crossdomain-tracking.md`

### 4. 🟥 Unknown Server Container Active
- Server-side container `GTM-M7BMM8ZQ` discovered (created by Temple Advertising)
- Uses same FB Pixel ID as Web container
- No consent controls; SFZC has view-only access  
📄 `task-server-container-audit.md`

---

## ✅ Task Tracker

| Task                            | Status        |
|---------------------------------|---------------|
| Enforce Consent Across Tags     | Not Started   |
| Remove UA and Migrate to GA4    | Not Started   |
| Configure Cross-Domain Tracking | Not Started   |
| Audit Server-Side Container     | Not Started   |
| Debugging Tools Reference       | Reference Only |

---

## 🧭 Next Steps

### 1. 🔧 **Begin with Low-Impact Task: Add “All Pages” Triggers**
- Identify critical tags that do **not** fire on all pages
- Safely enable `All Pages` trigger for consistent firing
- Validate using GTM Preview and Tag Assistant  
✅ Safe starting point that supports future consent and GA4 testing

### 2. Prioritize remaining tasks in this order:
- Consent enforcement (highest compliance risk)
- GA4-only migration (blocks UA deprecation)
- Cross-domain setup (required for fundraising funnel accuracy)
- Server container review (ownership/consent risk)
