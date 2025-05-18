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

---

## 📋 Fix Checklist
- [ ] GA4 config tag includes `linker.domains` array
- [ ] Site links are auto-linked or manually retain `_gl` tracking
- [ ] GA4 Realtime confirms session continuity across domains
- [ ] GTM Preview shows tag firing with `linker` active

---

## 🔄 Change Log
| Date       | Change                        | By         |
|------------|-------------------------------|------------|
| 2025-05-18 | Task doc created               | Assistant  |
