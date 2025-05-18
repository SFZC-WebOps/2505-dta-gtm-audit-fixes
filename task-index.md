---
# ✅ GTM Audit Task Index
> 📎 References: `auth.md` (canonical source of truth)

This file provides a high-level index of all implementation tasks related to the GTM audit and remediation project for SFZC.org. Each task file is modular, version-controlled, and references `auth.md` for canonical facts.

---

## 🗂️ Task File Directory

| Task File                             | Summary Description                                | Status     |
|--------------------------------------|----------------------------------------------------|------------|
| `task-fix-all-pages-trigger.md`       | Ensure base tags (GA4, Clarity, FB Pixel) fire on all pages | ⏳ In Progress |
| `task-consent-enforcement.md`         | Enforce cookie consent on all relevant tags via Cookiebot  | ⏳ In Progress |
| `task-crossdomain-tracking.md`        | Configure GA4 linker for give.sfzc.org & forms.sfzc.org     | ⏳ In Progress |
| `task-phase-out-ua.md`                | Remove all remaining UA (Universal Analytics) tags         | ⏳ In Progress |
| `task-folder-tagstructure-cleanup.md` | Organize GTM folder/tag naming and firing order             | ⏳ In Progress |
| `task-server-container-audit.md`      | Audit GTM-M7BMM8ZQ (server-side container) and define actions | ⏳ In Progress |
| `task-tools-debuggers.md`             | Central reference for testing/debugging tools               | ✅ Baseline Set |

---

## 📌 Notes
- Task files are self-contained and should **not modify or overwrite each other**.
- Each task references `auth.md` for confirmed container IDs and platform relationships.
- Status field is manually updated when tasks are started or completed.

---

## 🔁 How to Add New Tasks
1. Create a new file: `task-[slug].md`
2. Link it in the table above
3. Follow the structure: goal → problem → implementation → checklist → changelog

---

_Last updated: 2025-05-17_
