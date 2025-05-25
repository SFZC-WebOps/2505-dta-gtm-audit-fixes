---
# 📌 Task: Configure GA4 Cross-Domain Tracking
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Enable cross-domain user/session continuity across:
- `sfzc.org`
- `give.sfzc.org`
- `forms.sfzc.org`

---

## 🔍 Problem Statement
GA4 configuration tag is missing `linker_domains`. Cross-domain tracking is broken, leading to:
- Session loss between domains
- Duplicate user IDs
- Skewed analytics

---

## ⚠️ Prerequisites

- GA4 tag must already have consent settings implemented
- Consent enforcement task must be complete
- Test pages must be configured (`/test-page`)

---

## 🛠️ Implementation Plan

### ✅ Step 1: Update GA4 Config Tag

Add:
```javascript
'linker': {
  'domains': ['sfzc.org', 'give.sfzc.org', 'forms.sfzc.org']
}
```

### ✅ Step 2: Confirm Site Linker Auto-Link
Ensure links between domains either:
- Use gtag's `auto_link` capabilities, OR
- Have manual tracking parameters (`_gl`) preserved in links

### ✅ Step 3: Test Cross-Domain Navigation
- Click through from `sfzc.org` → `give.sfzc.org` and `forms.sfzc.org`
- Use Chrome DevTools or GTM Preview Mode to observe `_gl=` parameter
- Confirm continuity in GA4 Realtime and DebugView
- _gl Parameter Validation Guidelines (when testing cross-domain functionality, confirm that Google’s linker parameter (`_gl`) is preserved in the URL during navigation)
  - Example transition:
     From: `https://sfzc.org/events`
     To: `https://give.sfzc.org/donate?_gl=1*xyz123...`
  - **What to check:**
    - `_gl` parameter appears in the destination URL upon click-through
    - The value should persist during the session
    - GA4 DebugView should show continuous session (no new user ID or session start)
  - **Suggested Tools:**
    - Chrome DevTools → Network → check `document` request URLs
    - GTM Preview → Click the link and observe the generated navigation
    - GA4 Realtime → Validate that `page_view` or event is not a “new session” unless expected
    - 
  - Capture screenshots showing (confirms linker domains are functioning correctly):
    - `_gl` in the URL bar after cross-domain click
    - Matching session ID in GA4 before and after navigation

---

## 📋 Fix Checklist
- [ ] GA4 config tag includes `linker.domains` array
- [ ] Site links are auto-linked or manually retain `_gl` tracking
- [ ] GA4 Realtime confirms session continuity across domains
- [ ] GTM Preview shows tag firing with `linker` active

---

## 🔄 Change Log
| Date       | Change                                                | By         |
|------------|-------------------------------------------------------|------------|
| 2025-05-18 | Task doc created                                       | Assistant  |
| 2025-05-25 | Added rollback procedure section per Opus cross-check | Assistant  |
| 2025-05-25 | Added prerequisites section based on cross-check validation requirements | Assistant  |
| 2025-05-25 | Added tailored common errors section                  | Assistant  |
