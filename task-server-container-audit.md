# 📌 Task: Audit GTM Server Container (`GTM-M7BMM8ZQ`)
> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Determine the current status and compliance of the server-side GTM container (`GTM-M7BMM8ZQ`), and decide whether to retain, reconfigure, or decommission it.

---

## 🔍 Problem Statement
- Container was implemented by Temple Advertising
- SFZC team has view-only access
- Contains Facebook Conversions API tag
- No consent settings are configured
- Container use is undocumented and potentially redundant

---

## ⚠️ Prerequisites

- Consent enforcement must be validated (`task-consent-enforcement.md`)
- Access to DNS config or GA4 DebugView required to determine container use
- Confirm stakeholder position on server-side container ownership

---

## 🛠️ Audit Summary

### ⚠️ Configuration Details
| Property           | Value                                  |
|--------------------|----------------------------------------|
| Container ID       | GTM-M7BMM8ZQ                           |
| Purpose            | Facebook CAPI via GA4 client           |
| Consent Config     | ❌ Not Set                             |
| Last Editor        | belen.molinari@templeadv.com           |
| Current Access     | View-only                              |
| Duplicate Tag      | FB Pixel ID `1062378757459509`         |

---

## 🛠️ Recommended Actions

### ✅ Step 1: Confirm Usage
- Check if GA4 or other tags are routed to the server container
- Use DNS settings, GTM client logs, or GA4 DebugView

### ✅ Step 2: Review Legal and Risk Implications
- Validate whether CAPI events are being sent without consent
- Assess GDPR/CCPA exposure if true

### ✅ Step 3: Contact Contractor or Disable
- Try to regain access from Temple Advertising
- If no access and non-critical, recommend disabling container

### ✅ Step 4: Enforce Consent If Retained
- Add conditional triggers based on granted consent
- Use server-side logic to mirror Cookiebot status

### ✅ Step 5: Align with Stakeholder Decision
- Dan Belsky (IT Director) confirmed SFZC does not rely on this container.
- Unless a vendor confirms legitimate usage, proceed with shutdown.

---

## 📋 Decision Checklist
- [ ] Confirm if container is in active use
- [ ] GA4 or FB integration confirmed or rejected
- [ ] Access path or point-of-contact established
- [ ] Consent logic enforced or container disabled

---

## ⚠️ Common Errors

- Mistaking view-only access for active control — changes cannot be made without ownership
- Overlooking consent settings in server-side tags (e.g., Facebook CAPI firing without gating)
- Duplicate tracking from both web and server-side GTM containers (same Pixel ID)
- Failure to confirm server container use through DNS or GA4 DebugView before decommissioning
- Miscommunication with external vendor (Temple Advertising) delaying resolution

---

## 🔄 Rollback Procedure

If issues arise after implementation:

- Revert to previously exported GTM container version (`v15` or tagged snapshot)
- Pause or delete new/modified tag(s) associated with this task
- Restore known-good tag configurations as documented in GTM history or this task file
- Validate with GTM Preview + Consent Debugger before re-enabling changes

---

## 🔄 Change Log
| Date       | Change                                                                    | By         |
|------------|---------------------------------------------------------------------------|------------|
| 2025-05-18 | Task doc created                                                           | Assistant  |
| 2025-05-19 | Clarified that stakeholder has not reviewed or confirmed server container | Greg Bilke |
| 2025-05-25 | Added rollback procedure section per Opus cross-check                     | Assistant  |
| 2025-05-25 | Added prerequisites section based on cross-check validation requirements  | Assistant  |
| 2025-05-25 | Added tailored common errors section                                      | Assistant  |
