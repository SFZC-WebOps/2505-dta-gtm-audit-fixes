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

## 📋 Current Task Overview

| Task File                          | Summary                                                                 | Status       | Next Action                                                                 |
|-----------------------------------|-------------------------------------------------------------------------|--------------|------------------------------------------------------------------------------|
| `task-consent-enforcement.md`     | Enforce Cookiebot consent mode across all 24 tags.                      | Planning     | Apply `consentSettings` to one test tag and validate with Consent Debugger. |
| `task-crossdomain-tracking.md`    | Add GA4 linker config for session continuity across `sfzc.org` domains. | Not Started  | Update GA4 Configuration tag with `linker_domains`; test GA4 session flow.  |
| `task-phase-out-ua.md`            | Remove `UA-1720237-1` tags and replace with GA4 equivalents.            | Not Started  | Identify all UA tags; replicate events using GA4; test and deprecate UA.    |
| `task-server-container-audit.md`  | Audit undocumented server-side GTM container `GTM-M7BMM8ZQ`.            | In Review    | Confirm if it is active via DNS or GA4; decide to retain or decommission.   |
| `task-clarity-implementation.md`  | Implement Microsoft Clarity heatmap tracking via GTM.                   | Not Started  | Add Clarity script tag via GTM with consent; validate with GTM + Clarity UI.|
| `task-datalayer-schema.md`        | Document current dataLayer schema for donation, event, and user data.  | Not Started  | Audit existing `dataLayer` pushes on key pages; map all available keys.     |
| `task-testing-strategy.md`        | Define environment and testing process for safe GTM changes.            | Not Started  | Choose GTM environments or use `URL contains /test-page` trigger structure. |
| `task-tools-debuggers.md`         | Tool guide for validating tags, consent, and data flow.                 | Reference    | Use for all implementation QA and consent validation steps.                 |

---

## 🚩 Risks, Dependencies & Recommendations

| Area                        | Issue or Concern                                                                 |
|-----------------------------|----------------------------------------------------------------------------------|
| ❌ Consent Enforcement       | No tags currently enforce consent. This creates GDPR/CCPA compliance risk.      |
| ⚠️ Server Container Unknowns | View-only server-side GTM container (`GTM-M7BMM8ZQ`) is undocumented.            |
| ⚠️ UA Tags Active            | Deprecated `UA-1720237-1` tags still firing. May distort metrics and audits.    |
| 🔍 Tag Coverage              | Several tags are not firing on "All Pages" and have incomplete trigger setup.   |
| ⚠️ Tag Load Order            | No tag sequencing logic in place (e.g., Cookiebot must fire before analytics).  |
| 🧪 No Testing Plan           | No defined staging, preview, or rollback strategy for published changes.       |
| 📉 Tooling Dependency        | Validation requires use of Consent Debugger, GA4 DebugView, Omnibug, etc.       |

---

### 📌 Task Dependency Map

```plaintext
                          ┌──────────────────────────┐
                          │  task-consent-enforcement│
                          └────────────┬─────────────┘
                                       │
        ┌──────────────────────────────┼──────────────────────────────┐
        │                              │                              │
┌───────▼────────┐       ┌─────────────▼─────────────┐     ┌──────────▼─────────┐
│task-clarity-   │       │task-phase-out-ua          │     │task-crossdomain-   │
│implementation  │       │                           │     │tracking            │
└────────────────┘       └───────────────────────────┘     └────────────────────┘

                          ┌──────────────────────────┐
                          │task-server-container-    │
                          │audit                     │
                          └──────────────────────────┘

                          ┌──────────────────────────┐
                          │task-datalayer-schema     │
                          └──────────────────────────┘

                          ┌──────────────────────────┐
                          │task-testing-strategy     │
                          └──────────────────────────┘

                          ┌──────────────────────────┐
                          │task-tools-debuggers      │ (Reference tool)
                          └──────────────────────────┘
```

---

## ✅ Suggested First Task

**Start with: `task-consent-enforcement.md`**

- It has **low implementation risk**
- Provides **clear benefit** by addressing legal compliance
- Must be completed before rolling out additional tracking changes

---

## 📎 Reference Notes

- `auth.md` is the canonical authority for all container IDs, tracking IDs, and platform truths.
- Each task file tracks its own scope and must preserve historical entries (append-only).
- See `task-index.md` for full task listing, statuses, and change logs.