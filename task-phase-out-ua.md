---
# 📌 Task: Phase Out Universal Analytics (UA) Tags
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Safely remove all remaining `UA-1720237-1` (Universal Analytics) tags and replace with GA4 equivalents.

---

## 🔍 Problem Statement
- UA is deprecated as of July 2023 - Not to be used in SFZC production environment
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
- **Parameter Mapping:** Confirm that UA parameters (`event_category`, `event_action`, `event_label`) are mapped to GA4 custom parameters (e.g., `event_category` → `category`, or via `event_name` and `event_params`)
- **Event Naming:** Ensure event names follow GA4 conventions (e.g., `button_click`, `form_submit`, `donation_start`) rather than UA-style labels
- **Realtime View:** Use GA4 Realtime and DebugView to validate that:
  - The event fires on correct trigger
  - All expected parameters appear under `event_params`
  - Event matches naming and structure defined in GA4 Admin > Events

Use consistent page interaction (e.g., clickstream or form submission) to trigger both UA and GA4 versions for side-by-side comparison before fully deprecating UA.

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
