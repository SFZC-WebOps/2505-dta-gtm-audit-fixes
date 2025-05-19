---
# 📌 Task: Enforce Consent Settings Across All Tags
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Ensure that **all tags requiring user consent** have `consentSettings` properly configured and enforced via Cookiebot CMP integration.

---

## 🔍 Problem Statement
Audit of `GTM-TGH83XK` (v15) revealed:
- All 24 tags lacked `consentSettings`
- Cookiebot CMP tag exists but is not linked to tag behavior
- Tags may fire before consent is granted (GDPR/CCPA risk)

---

### 🧑‍💼 Stakeholder Policy Directive
Per IT Director Dan Belsky:
- SFZC must comply with GDPR/CCPA requirements.
- Cookiebot must control all tag firing behavior.
- No exceptions for marketing or analytics tags.

---

## 🛠️ Implementation Plan

### ✅ Step 1: Tag-by-Tag Consent Review
For each tag, determine if it requires:
- `ad_storage`
- `analytics_storage`
- Other categories (e.g., `functionality_storage`)

### ✅ Step 2: Configure Consent Settings
For each tag:
```json
"consentSettings": {
  "consentRequired": true,
  "consentTypes": ["ad_storage", "analytics_storage"]
}
```

### ✅ Step 3: Integrate with Cookiebot
- Ensure Cookiebot tag (ID `28`) fires early
- Use GTM event listeners like `CookieConsentDeclaration` or `CookieConsentAccepted`

### ✅ Step 4: Validate
- Use GTM Preview Mode with Consent Mode Debugger
- Confirm tags wait for granted consent before firing

---

## 📋 Fix Checklist
- [ ] All tracking tags have `consentSettings` field
- [ ] Cookiebot fires on all pages (before other tags)
- [ ] Consent categories match tag purpose
- [ ] Validation complete with Consent Debugger

---

## 🔄 Change Log

| Date       | Change                                                                 | By         |
|------------|------------------------------------------------------------------------|------------|
| 2025-05-18 | Task doc created                                                        | Assistant  |
| 2025-05-19 | Added stakeholder directive requiring consent enforcement for all tags | Greg Bilke |
