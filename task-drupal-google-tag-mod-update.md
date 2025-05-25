# 📌 Task: GTM Module Update
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Update Google Tag module from 2.0.6 to latest security release 2.0.8

---

## 🔍 Problem Statement
- Kalamuna must do work
- This update blocks all tag publishing actions due to GTM module instability on 2.0.6
- **No other tag tasks** can proceed until this is complete

---

## ⚠️ Prerequisites

- Drupal admin access must be available to confirm module update
- GTM Preview Mode and Consent Debugger must be functional
- Consent enforcement must be in place to evaluate post-update behavior

---

## 🛠️ Implementation Plan

### ✅ Step 1: Coordinate with Kalamuna
- Request update of `google_tag` module to version 2.0.8
- Confirm inclusion of any required dependencies or core updates

### ✅ Step 2: Verify Module Update
- Use Drupal admin UI or `drush pm:list` to confirm version 2.0.8 is active
- Expected version string: `google_tag 8.x-2.0.8`

### ✅ Step 3: Validate GTM Functionality
- Load GTM Preview Mode for the site
- Confirm that GTM container loads and triggers fire as expected
- Verify that no JavaScript errors appear in the browser console
- Confirm Cookiebot CMP fires early and still gates analytics and marketing tags
- Check that core tags (GA4, Clarity, Facebook Pixel) fire only after consent

---

## 📋 Fix Checklist
- [ ] Drupal module version updated to 2.0.8
- [ ] GTM loads on all pages without JavaScript errors
- [ ] Cookiebot fires on all pages and blocks tags prior to consent
- [ ] Core tags fire as expected after consent (GA4, Clarity, Facebook)
- [ ] Validation completed in GTM Preview and Consent Debugger

---

## ⚠️ Common Errors

- Module update applied but site cache not cleared → GTM appears missing
- Cookiebot or GTM scripts fail due to missing `<head>` injection after update
- Old GTM snippets manually inserted in theme override module behavior
- Tags silently fail due to missing consent logic or configuration drift
- No confirmation step or version check performed post-deploy

---

## 🔄 Rollback Procedure

If issues arise after implementation:

- Revert to previously exported GTM container version (`v15` or tagged snapshot)
- Pause or delete new/modified tag(s) associated with this task
- Restore known-good tag configurations as documented in GTM history or this task file
- Validate with GTM Preview + Consent Debugger before re-enabling changes

---

## 🔄 Change Log
| Date       | Change                                                                                     | By         |
|------------|--------------------------------------------------------------------------------------------|------------|
| 2025-05-18 | Task doc created                                                                            | Assistant  |
| 2025-05-25 | Added rollback procedure section per Opus cross-check                                      | Assistant  |
| 2025-05-25 | Added prerequisites section based on cross-check validation requirements                   | Assistant  |
| 2025-05-25 | Added tailored common errors section                                                       | Assistant  |
| 2025-05-25 | Expanded implementation and validation steps for clarity                                   | Assistant  |
