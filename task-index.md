# 🧩 GTM Task Index
> This file indexes all scoped tasks (`task-*.md`) in the 2505-DTA-GTM-Audit-Fixes project.
> Each task is maintained in its own markdown file with implementation steps, audit notes, and changelogs.

---

## 📁 Task Files Overview

| Task File                          | Description                                                       | Status       |
|-----------------------------------|-------------------------------------------------------------------|--------------|
| `task-consent-enforcement.md`     | Enforce Cookiebot consent mode across all GTM tags                | In progress  |
| `task-crossdomain-tracking.md`    | Configure GA4 linker for session continuity between subdomains    | In progress  |
| `task-phase-out-ua.md`            | Remove Universal Analytics tags and migrate events to GA4         | In progress  |
| `task-server-container-audit.md`  | Audit server-side container `GTM-M7BMM8ZQ` and resolve ownership  | In review    |
| `task-tools-debuggers.md`         | Reference tools and debugging methods for validating GTM setup    | Reference    |

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
- `README.md` gives the project overview and structure
- `memory.md` provides a timeline of cross-task milestones

This approach avoids duplication and ensures detailed tracking without bloating the central memory file.

Use this index as your central map to navigate the active and historical GTM work.

---

## 🔄 Change Log

| Date       | Change                                                                   | By         |
|------------|--------------------------------------------------------------------------|------------|
| 2025-05-19 | Updated task statuses and descriptions based on current implementation phase | Greg Bilke |
