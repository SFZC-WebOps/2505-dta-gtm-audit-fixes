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

## ⚠️ Prerequisites

- Chrome DevTools must be available for in-browser inspection
- Consent enforcement task must be completed (if gating applies to dataLayer pushes)
- Test pages or real-use paths (donate, events, user account) must be accessible

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

## ⚠️ Common Errors

- Forgetting to capture `dataLayer` pushes triggered by user interaction (not just pageload)
- Overlooking asynchronous script-based injections that modify `dataLayer`
- Mapping keys that change format between different page types (e.g., donation vs. retreat events)
- Schema examples not updated after a Drupal or Classy update
- Assuming flat key structures without checking for nested objects


---

## 🔄 Change Log
| Date       | Change                                                      | By         |
|------------|-------------------------------------------------------------|------------|
| 2025-05-18 | Task doc created                                             | Assistant  |
| 2025-05-21 | Added priority page types and structured audit instructions | Assistant  |
| 2025-05-25 | Added rollback procedure section per Opus cross-check       | Assistant  |
| 2025-05-25 | Added prerequisites section based on cross-check validation requirements | Assistant  |
| 2025-05-25 | Added tailored common errors section                        | Assistant  |
