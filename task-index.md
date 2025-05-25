# 🧩 GTM Task Index
> This file indexes all scoped tasks (`task-*.md`) in the 2505-DTA-GTM-Audit-Fixes project.
> Each task is maintained in its own markdown file with implementation steps, audit notes, and changelogs.

---

## 📁 Task Files Overview

| Task File                          | Goal                                             | Status       | Next Action                          | ETA (days) | Dependency                  |
|-----------------------------------|--------------------------------------------------|--------------|---------------------------------------|------------|-----------------------------|
| `task-consent-enforcement.md`     | Enforce consent settings on all tags             | ✅ Complete   | Final validation before publish      | 0          | Requires Cookiebot active   |
| `task-crossdomain-tracking.md`    | Restore GA4 session continuity across domains    | ✅ Complete   | Deploy linker updates after consent  | 1          | Consent enforcement         |
| `task-datalayer-schema.md`        | Document current Drupal `dataLayer` structure    | ✅ Complete   | Integrate schema into tag config     | 2          | Site access                 |
| `task-drupal-google-tag-mod-update.md` | Update insecure GTM module version          | ✅ Complete   | Await deployment confirmation        | 1–2        | Kalamuna contractor         |
| `task-clarity-implementation.md`  | Implement Clarity via GTM                        | ✅ Complete   | Tag test & publish post-consent      | 1          | Consent enforcement         |
| `task-phase-out-ua.md`            | Remove deprecated UA tracking                    | ✅ Complete   | Fully disable after GA4 validation   | 2          | GA4 validated                |
| `task-server-container-audit.md`  | Audit server-side container `GTM-M7BMM8ZQ`       | ✅ Complete   | Follow up with vendor or decommission | 2          | Temple Advertising contact  |

---

## 🧭 Status Key
- ✅ Complete – Task file fully documented and approved
- 🚧 In Progress – Implementation partially done
- 🕒 Pending – Awaiting dependency or stakeholder input
- ❌ Deprecated – Cancelled or replaced
