# 📌 Task: Data Layer Schema
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Document current `dataLayer` schema for donation, event, and user data.

---

## 🔍 Problem Statement
- No documented structure for `dataLayer` keys currently exists
- Tag design and GA4 mapping cannot proceed without clarity on available variables

---

## 🛠️ Implementation Plan

### ✅ Step 1: Audit Key Pages
Target the following page types:
- `/donate` (Classy or embedded donation forms)
- `/events`, `/retreats`, or calendar detail pages
- Logged-in areas, login/logout paths, and user actions

### ✅ Step 2: Inspect `dataLayer` Pushes
- Use Chrome DevTools → Console → `dataLayer` to print contents
- Record all keys and nested objects pushed on pageload or interaction

### ✅ Step 3: Build Schema Documentation
- Capture samples of each major push
- Map available keys to GA4 parameter equivalents

---

## 📋 Fix Checklist
- [ ] All priority page types audited
- [ ] Example dataLayer entries collected
- [ ] Keys mapped to intended GA4 parameters
- [ ] Exportable schema reference generated

---

## 🔄 Change Log
| Date       | Change                                                      | By         |
|------------|-------------------------------------------------------------|------------|
| 2025-05-18 | Task doc created                                             | Assistant  |
| 2025-05-21 | Added priority page types and structured audit instructions | Assistant  |
