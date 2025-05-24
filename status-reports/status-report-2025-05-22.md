# ✅ GTM Tracking Reset: Project Status Report  
**Date:** Thursday, May 22, 2025  
**Contact:** Greg Bilke, SFZC WebOps  
**Project Code:** `2505-DTA-GTM-Audit-Fixes`  
**Canonical Source:** [`auth.md`](auth.md)  

---

## 📌 Project Summary

This project was initiated to review, document, and correct issues in the GTM tracking implementation for SFZC.org, including compliance gaps, configuration drift, and legacy contractor work. We are working from an exported GTM container (`GTM-TGH83XK`, version 15) and have documented all findings in individual task files to ensure traceability and compliance with GDPR/CCPA regulations.

### GTM Container Under Review
| Property         | Value               |
|------------------|---------------------|
| Container ID     | `GTM-TGH83XK`       |
| Platform         | Web                 |
| Export Version   | v15                 |
| Export Date      | 2025-05-16          |
| GA4 ID           | `G-BRXZCXMZP5`      |
| UA ID (Legacy)   | `UA-1720237-1`      |
| Clarity ID       | `rfyzkzgfcs`        |
| CMP              | Cookiebot (`eb8e5eb5-...`) |

---

## 📋 Current Task Overview (Sequenced)

| Task File                          | Summary                                                                 | Status       | Next Action                                                                 |
|-----------------------------------|-------------------------------------------------------------------------|--------------|------------------------------------------------------------------------------|
| `task-server-container-audit.md`  | Audit undocumented server-side GTM container `GTM-M7BMM8ZQ`.            | In Review    | Export confirms Facebook CAPI tag with `ALWAYS` trigger and `consentStatus: NOT_SET`. Pixel ID duplicates Web. High GDPR/CCPA risk. Decision pending. |
| `task-update-drupal-google-tag.md`     | Update Google Tag module from 2.0.6 to latest security release 2.0.8 | Not Started  | Upgrade module before any further GTM or tag changes; validate post-update. |
| `task-testing-strategy.md`        | Define environment and testing process for safe GTM changes.            | Not Started  | Choose GTM environments or use `URL contains /test-page` trigger structure. |
| `task-consent-enforcement.md`     | Enforce Cookiebot consent mode across all 24 tags.                      | Planning     | Apply `consentSettings` to one test tag and validate with Consent Debugger. |
| `task-tools-debuggers.md`         | Tool guide for validating tags, consent, and data flow.                 | Reference    | Use for all implementation QA and consent validation steps.                 |
| `task-datalayer-schema.md`        | Document current dataLayer schema for donation, event, and user data.   | Not Started  | Audit existing `dataLayer` pushes on key pages; map all available keys.     |
| `task-clarity-implementation.md`  | Implement Microsoft Clarity heatmap tracking via GTM.                   | Not Started  | Add Clarity script tag via GTM with consent; validate with GTM + Clarity UI.|
| `task-phase-out-ua.md`            | Remove `UA-1720237-1` tags and replace with GA4 equivalents.            | Not Started  | Identify all UA tags; replicate events using GA4; test and deprecate UA.    |
| `task-crossdomain-tracking.md`    | Add GA4 linker config for session continuity across `sfzc.org` domains. | Not Started  | Update GA4 Configuration tag with `linker_domains`; test GA4 session flow.  |

---

## 🚩 Risks, Dependencies & Recommendations

| Area                        | Issue or Concern                                                                 |
|-----------------------------|----------------------------------------------------------------------------------|
| ❌ Consent Enforcement       | No tags currently enforce consent. This creates GDPR/CCPA compliance risk.      |
| ❌ Server Container Fires Without Consent | Export confirms Facebook CAPI tag fires on all events with no consent settings (`NOT_SET`). Uses same Pixel ID as Web. View-only access. High privacy risk. |
| ⚠️ UA Tags Active            | Deprecated `UA-1720237-1` tags still firing. May distort metrics and audits.    |
| 🔍 Tag Coverage              | Several tags are not firing on "All Pages" and have incomplete trigger setup.   |
| ⚠️ Tag Load Order            | No tag sequencing logic in place (e.g., Cookiebot must fire before analytics).  |
| 🧪 No Testing Plan           | No defined staging, preview, or rollback strategy for published changes.       |
| 📉 Tooling Dependency        | Validation requires use of Consent Debugger, GA4 DebugView, Omnibug, etc.       |

---

### 📌 Task Dependency Map

```plaintext
                          ┌──────────────────────────────┐
                          │task-server-container-audit   │
                          └────────────┬─────────────────┘
                                       │
                          ┌────────────▼─────────────┐
                          │task-update-drupal-google-tag │
                          └────────────┬─────────────────┘
                                       │
                          ┌────────────▼─────────────┐
                          │task-testing-strategy     │
                          └────────────┬─────────────┘
                                       │
                          ┌────────────▼─────────────┐
                          │  task-consent-enforcement│
                          └────────────┬─────────────┘
                                       │
                          ┌────────────▼─────────────┐
                          │task-testing-strategy     │
                          └────────────┬─────────────┘
                                       │
                ┌──────────────────────┼──────────────────────┐
                │                      │                      │
        ┌───────▼────────┐     ┌───────▼─────────────┐ ┌──────▼────────────┐
        │task-clarity-   │     │task-phase-out-ua    │ │task-crossdomain-  │
        │implementation  │     │                     │ │tracking           │
        └────────────────┘     └─────────────────────┘ └────────────────────┘

                          ┌──────────────────────────┐
                          │task-datalayer-schema     │
                          └──────────────────────────┘

                          ┌──────────────────────────┐
                          │task-server-container-    │
                          │audit                     │
                          └──────────────────────────┘

                          ┌──────────────────────────┐
                          │task-tools-debuggers      │ (Reference tool)
                          └──────────────────────────┘
```

---

## ✅ Suggested First Task

**Start with: `task-update-drupal-google-tag.md`**

- It has **low implementation risk**
- Required for security compliance before implementing tag changes
- Provides **clear benefit** by addressing legal compliance
- Must be completed before rolling out additional tracking changes

---


---

## 🕒 Estimated GTM Project Timeline (Padded for Learning Curve)

| Phase | Task Group | Estimated Time (Padded) | Dependency |
|-------|------------|--------------------------|------------|
| **Phase 1** | `task-server-container-audit.md` (final action) | 2–4 days | Requires response from Temple or internal decision to shut down |
| **Phase 2** | `task-update-drupal-google-tag.md` | ⏳ _Blocked_ — Needs Drupal contractor (estimate: 3–5 days once scheduled) | Must complete before any tag changes |
| **Phase 3** | `task-testing-strategy.md`, `task-tools-debuggers.md` | 3–5 days | Needed before applying consent enforcement |
| **Phase 3** | `task-testing-strategy.md`, `task-datalayer-schema.md` | 4–6 days | Can begin while validating consent changes |
| **Phase 4** | `task-clarity-implementation.md` | 2–3 days | Depends on validated consent and test flow |
| **Phase 5** | `task-phase-out-ua.md`, `task-crossdomain-tracking.md` | 4–6 days | Only safe after consent + testing confirmed |
| **Phase 6** | `task-server-container-audit.md` (final action) | 2–4 days | Requires response from Temple or internal decision to shut down |

---

### ✅ Total Estimated Duration (excluding Drupal delay):  
**~15–25 working days**

Use this as a pacing guide — phases are designed to build confidence and minimize risk at each step.

## 📎 Reference Notes

- `auth.md` is the canonical authority for all container IDs, tracking IDs, and platform truths.
- Each task file tracks its own scope and must preserve historical entries (append-only).
- See `task-index.md` for full task listing, statuses, and change logs.