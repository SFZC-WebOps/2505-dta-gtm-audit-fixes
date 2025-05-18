---
# 📌 Task: Phase Out Universal Analytics (UA) Tags
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Safely remove all remaining `UA-1720237-1` (Universal Analytics) tags and replace with GA4 equivalents.

---

## 🔍 Problem Statement
- UA is deprecated as of July 2023
- Tags using `UA-1720237-1` still exist in GTM container `GTM-TGH83XK`
- Continuing to use UA tags risks inaccurate tracking and unsupported behavior

---

## 🛠️ Implementation Plan

### ✅ Step 1: Identify All UA Tags
- Filter for `Tag Type: Universal Analytics` in GTM
- Catalog tags using UA Tracking ID: `UA-1720237-1`

### ✅ Step 2: Review Purpose
For each UA tag, determine:
- Is this a pageview or event tag?
- What are the GA4 equivalent parameters?

### ✅ Step 3: Rebuild in GA4
- Use GA4 Event or GA4 Configuration tags
- Map UA event structure to GA4 (`event_category`, `event_action`, `event_label` → GA4 custom parameters)

### ✅ Step 4: Disable or Remove UA Tags
- Pause tags in GTM, or delete after GA4 coverage is confirmed
- Leave comments or change log notes on deprecations

### ✅ Step 5: Validate
- Test GA4 versions using GTM Preview and GA4 DebugView
- Confirm matching event names and parameters in GA4 Realtime

---

## 📋 Fix Checklist
- [ ] All UA tags identified and documented
- [ ] GA4 equivalents created and tested
- [ ] UA tags paused or removed
- [ ] GA4 event parameters verified in DebugView

---

## 🔄 Change Log
| Date       | Change                        | By         |
|------------|-------------------------------|------------|
| 2025-05-18 | Task doc created               | Assistant  |
