# 🧩 GTM Task Index
> This file indexes all scoped tasks (`task-*.md`) in the 2505-DTA-GTM-Audit-Fixes project.
> Each task is maintained in its own markdown file with implementation steps, audit notes, and changelogs.

---

## 📁 Task Files Overview

| Task File                          | Goal                                             | Status       | Next Action | ETA (days) | Dependency |
|-----------------------------------|-------------------------------------------------------------------|--------------|-----------------------------------|-----------------------------------|-----------------------------------|
| **Phase: Server Container ** |  |  |  |  |  |
| `task-server-container-audit.md` | Audit server-side container `GTM-M7BMM8ZQ` and resolve ownership | In review | Export confirms Facebook CAPI tag with `ALWAYS` trigger and `consentStatus: NOT_SET`. Pixel ID duplicates Web. High GDPR/CCPA risk. Decision pending. | 2-4 | Requires response from Temple or internal decision to shut down |
| **Phase: GTM Module Update ** |  |  |  |  |  |
| `task-drupal-google-tag-mod-update.md` | Update Google Tag module from 2.0.6 to latest security release 2.0.8 | ⏳ _Blocked_ — Kalamuna contacted - Awaiting response | Upgrade module before any further GTM or tag changes; validate post-update. | (estimate: 3–5 days once scheduled) | Must complete before any tag changes |
| **Phase: Testing & Documenting ** |  |  |  |  |  |
| `task-testing-strategy.md` | Define environment and testing process for safe GTM changes | ✅ Complete | Local testbed with consent/debug tooling validated on 2025-05-24 | 0 | Enables consent enforcement + Clarity testing |
| `task-datalayer-schema.md` | Document current dataLayer schema for donation, event, and user data. | ⏳ Not Started | Audit `dataLayer` pushes and export schema documentation | 1-2 | Can proceed in parallel with consent testing |
| **Phase: Consent** |  |  |  |  |  |
| `task-consent-enforcement.md` | Enforce Cookiebot consent mode across all 24 tags | Not Started | Apply `consentSettings` to GA4 tag and validate via Consent Debugger | 2-4 | After testing and documentation has been confirmed |
| **Phase: Main Tasks ** |  |  |  |  |  |
| `task-clarity-implementation.md` | Implement Microsoft Clarity via GTM with consent and test validation | Not Started | Add Clarity script tag via GTM with consent; validate with GTM + Clarity UI. | 2-3 | Only safe after consent + testing confirmed |
| `task-phase-out-ua.md` | Remove Universal Analytics tags and migrate events to GA4    | Not Started | Identify all UA tags; replicate events using GA4; test and deprecate UA. | 2-3 | Only safe after consent + testing confirmed |
| `task-crossdomain-tracking.md`    | Configure GA4 linker for session continuity between subdomains    | Not Started  | Update GA4 Configuration tag with `linker_domains`; test GA4 session flow. | 4-6 | Only safe after consent + testing confirmed |

### ✅ Total Estimated Duration (excluding Drupal delay):  

**~15–25 working days**

Use this as a pacing guide — phases are designed to build confidence and minimize risk at each step.

---

## 🛠 Task Structure Template
Each task file follows this format:

- **🎯 Goal** – What are we trying to fix or implement?
- **🔍 Problem Statement** – Why is this task needed?
- **🛠️ Implementation Plan** – Step-by-step fix plan
- **📋 Fix Checklist** – Boxed list of completion steps
- **🔄 Change Log** – Timestamped record of edits or completions

---

## 🔄 Task Management Principles
- Tasks should not overwrite each other — preserve full historical record
- All edits must be traceable to a GTM export, validation session, or published version
- Task files can be referenced in commits, Git tags, or stakeholder reviews

> 📎 Reference: `auth.md` is always the canonical source for container IDs, owners, and environment details

---

## 🧠 Memory Strategy for Task Files
Each `task-*.md` file serves as a **self-contained memory log** for its specific area of work:

- All implementation history is tracked in the file itself

This approach avoids duplication and ensures detailed tracking without bloating the central memory file.

Use this index as your central map to navigate the active and historical GTM work.

---

## 🔄 Change Log

| Date       | Change                                                       | By         |
| ---------- | ------------------------------------------------------------ | ---------- |
| 2025-05-19 | Updated task statuses and descriptions based on current implementation phase | Greg Bilke |
| 2025-05-23 | Refined task statuses, actions, and ETA/dependency logic post-audit | Assistant  |
| 2025-05-24 | Marked `task-testing-strategy.md` as complete after consent-mode testing validation | Greg Bilke (GB) |
