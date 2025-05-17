---

# 🧠 Project Memory: 2505-DTA-GTM-Updates-Troubleshooting

> This is the authoritative memory record for the SFZC.org GTM troubleshooting and implementation project. **DO NOT REMOVE OR ALTER PREVIOUS CONTENT** unless explicitly instructed. Append new verified findings only.

---

## 📓 Change Log

| Date       | Update Summary                                               | By                   |
|------------|--------------------------------------------------------------|----------------------|
| 2025-05-12 | Initial merged memory created from two task threads          | Greg Bilke           |
| 2025-05-13 | Verified Clarity tracking code and implementation plan added | Assistant            |
| 2025-05-14 | Added GTM Health Check task and Cookiebot concern            | Assistant            |
| 2025-05-15 | Added GTM container export (v15) - Did audit of any issue    | Greg Bilke - Assistant |
| 2025-05-17 | Reorganized memory into implementation-focused format        | Assistant            |

---

## 📌 Project Overview

- **Project Name**: GTM Troubleshooting & Audit for SFZC.org
- **GTM Container ID**: `GTM-TGH83XK`
- **Audit Initiated**: May 15, 2025
- **Purpose**: Conduct a comprehensive audit of GTM implementation on SFZC.org, identify misconfigurations, and document recommended improvements to support future implementation clarity.
- **Environment**: Pantheon-hosted Drupal 9 site
- **Workspace**: Web
- **Export File (v15)**: `GTM-TGH83XK_v15.json`
- **Container Export Date**: 2025-05-16 22:40:56

---

## 🧩 Current State Snapshot (as of GTM v15)

### ✅ GTM Container Summary
- **Tags**: 24
- **Triggers**: 19
- **Variables**: 98
- **Built-in Variables**: 14
- **Custom Templates**: 1
- **Environment**: Web

### ⚠️ Google Tag Manager Diagnostics (via UI)
- **Issue 1**: Additional domains detected — tags firing on domains not listed in GA4 domain config.
- **Issue 2**: Some pages not tagged — Trigger misconfigurations or GTM not deployed across full site.
- **Issue 3**: Missing Google tags — GA4 not deployed using latest gtag.js structure.

### 🔍 Audit Findings (from: `gtm-container-audit-GTM-TGH83XK-v15.md`)
- **Tags NOT Firing on “All Pages”**:
  - All 24 tags had specific or missing triggers
  - Includes GA4 config, MS Clarity, FB Pixel, Classy events, YouTube tracking
- **Consent Settings Missing**:
  - All 24 tags lacked explicit `consentSettings` with `GRANTED` status
  - Cookiebot CMP tag exists, but enforcement is missing
- **Cross-Domain Gaps**:
  - `GA4 Configuration - G-BRXZCXMZP5` is missing `linker_domains` config
  - No setup for `give.sfzc.org`, `forms.sfzc.org`, etc.

---

## 🛠️ Fix-It Roadmap (from: `gtm-container-fix-checklist-GTM-TGH83XK-v15.md`)

### Fix 1: Add “All Pages” Trigger Where Appropriate
- Review and apply All Pages firing on:
  - GA4 config
  - MS Clarity
  - Meta Pixel base
  - Pardot pageview
  - Conversion Linker

### Fix 2: Enforce Consent Across All Tags
- Add explicit `consentSettings` to all tracking and marketing tags
- Integrate with existing Cookiebot CMP (tag ID 28)
- Verify wait time and default consent config

### Fix 3: Configure Cross-Domain Tracking
- Add `linker_domains` to GA4 config:
  - `give.sfzc.org`, `forms.sfzc.org`, `sfzc.pantheon.io`
- Ensure GA4 uses gtag.js properly with updated structure

### Fix 4: Phase Out UA Tags
- Tag types like `ua` (Universal Analytics) are still active
- Replace or deprecate in favor of GA4 equivalents

### Fix 5: Folder Structure & Naming
- Normalize folder usage (e.g., Classy, Main GA, Facebook)
- Remove legacy or unused folders after migration

### Fix 6: Tag Sequencing / Load Order
- Prioritize base tags (GA4, Cookiebot) before any event-specific tags
- Consider using tag sequencing or priority fields (e.g., `priority: 100` for FB base)

### Optional Debug Step
- Enable Consent Mode Debugger
- Use GTM Preview + Tag Assistant + Cookiebot console validation

---

## 🛠️ Tools & Procedures (Diagnostic and Implementation Support)

This section documents verified tools and workflows used during the GTM audit and implementation work. It will expand with more detail as specific tasks are executed.

### 🔍 Tag & Consent Debugging
- **Google Tag Assistant** (Preview Mode): Essential for visualizing tag firing behavior and consent status
- **Google Consent Mode Debugger**: Chrome extension to verify consent categories passed to gtag.js
- **Omnibug**: Browser extension to inspect all outbound analytics tags (GA4, FB, Clarity, etc.)

### 📦 GTM Management Tools
- **GTM JSON Export / Import**: All container changes are tracked using versioned JSON exports
- **Container Versioning**: A new version is published only after validation of fixes via GTM preview tools

### 🧪 Test Methods
- Use temporary triggers (e.g., `URL contains /test-page`) to validate tags before applying to `All Pages`
- Use `gtag('consent', 'default', ...)` settings to test Consent Mode staging behavior

_This section will be expanded per task during implementation._

---

## 🧾 Tag Inventory (from JSON Export v15)

> 🗂️ Tags Total: 24 (not listed in full here — reference `GTM-TGH83XK_v15.json` for source)

Examples:
- `GA4 Configuration - G-BRXZCXMZP5`
- `Microsoft Clarity - Official`
- `Facebook Pixel - All Pages`
- `Conversion Linker`
- `Classy Transaction Completion (GA4)`
- `Classy Donation (FB)`
- `CU - YouTube Tracking`

All current tags lack consent enforcement.

---

## 📚 Historical Notes & Legacy References

- Project began prior to 2020; many unknown contractors modified GTM without documentation
- Tag duplication and redundant scripts detected in earlier sessions
- No consistent folder usage or naming conventions
- Consent enforcement introduced later with Cookiebot (tag exists but lacks integration)
- Multiple domains used for donation/events: `give.sfzc.org`, `classy.org`, `forms.sfzc.org`

---

## 🚀 Next Publish Plan (Upcoming GTM v16)

### Goals Before Publish:
- [ ] All base tags on All Pages
- [ ] Consent settings enforced or tagged for all consent-requiring tools
- [ ] Cross-domain tracking correctly configured in GA4
- [ ] No deprecated UA tag types
- [ ] Tag sequencing validated (base first, then events)

### Post-Publish Validation:
- [ ] Google Tag Assistant (Live preview)
- [ ] Consent Mode Debugger
- [ ] GA4 Realtime verification
- [ ] Conversion event flow checks

---

_End of current memory state — continue appending updates as new versions are prepared._
