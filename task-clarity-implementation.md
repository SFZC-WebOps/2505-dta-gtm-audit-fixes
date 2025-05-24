# 📌 Task: Microsoft Clarity Implementation via GTM
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Implement Microsoft Clarity via Google Tag Manager for session heatmapping and user interaction analysis on SFZC.org.

---

## 🔍 Problem Statement
- Clarity tracking ID `rfyzkzgfcs` is verified in `auth.md`
- No dedicated GTM tag or task file documents its setup
- Consent type: `analytics_storage`
- Tag Assistant audit shows the Clarity tag is **not firing on all pages**
- No current mechanism exists for testing or consent enforcement

---

## 🧑‍💼 Stakeholder Notes
- Per Dan Belsky: Clarity is approved for deployment if implemented through GTM and honors Cookiebot consent.

---

## 🛠️ Implementation Plan

### Dependency

This task should not go live until Consent Enforcement and Testing Strategy tasks are complete.

### ✅ Step 1: Build GTM Tag
- Use `Custom HTML` tag type
- Paste official Clarity script using ID `rfyzkzgfcs`
- Set tag name: `Microsoft Clarity - rfyzkzgfcs`

### ✅ Step 2: Apply Trigger
- Trigger: `All Pages`
- For testing: optionally use a temporary trigger `Page URL contains /test-page`

### ✅ Step 3: Add Consent Settings
```json
"consentSettings": {
  "consentRequired": true,
  "consentTypes": ["analytics_storage"]
}
```

### ✅ Step 4: Validate
- Use GTM Preview Mode
- Open `sfzc.org/test-page` and verify tag fires
- Use Microsoft Clarity dashboard to confirm data reception
- Use Consent Mode Debugger to confirm consent gating

### ✅ Step 5: Go Live
- Replace test trigger with `All Pages`
- Revalidate before publishing new container version

---

## 📋 Fix Checklist
- [ ] Clarity tag created with correct ID and type
- [ ] Tag fires on test URL and receives data
- [ ] Consent settings enforced
- [ ] Tag validated with GTM Preview and Clarity UI
- [ ] Tag enabled on All Pages and container published

---

## 🔄 Change Log

| Date       | Change                                             | By         |
|------------|----------------------------------------------------|------------|
| 2025-05-21 | Task created for Clarity GTM integration           | Assistant  |
