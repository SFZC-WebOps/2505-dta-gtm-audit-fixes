# 🧩 GTM Task Index
> This file indexes all scoped tasks (`task-*.md`) in the 2505-DTA-GTM-Audit-Fixes project.  
> Each task is maintained in its own markdown file with implementation steps, audit notes, and changelogs.

---

## 🗂️ Phase 1: Foundation & Environment Setup

| Task File                          | Goal                                          | Status        | Next Action                         | ETA (days) | Dependency            |
|-----------------------------------|-----------------------------------------------|---------------|-------------------------------------|------------|-----------------------|
| `task-datalayer-schema.md`        | Document current Drupal `dataLayer` structure | 🚧 In Progress | Integrate schema into tag config    | 0          | Site access            |
| `task-testing-strategy.md`        | Define controlled GTM testing workflow        | ✅ Complete    | Use in upcoming validations         | 0          | N/A                   |
| `task-drupal-google-tag-mod-update.md` | Update insecure GTM module version        | 🕒 Pending     | Await deployment confirmation       | 1–2        | Kalamuna contractor   |

---

## 🗂️ Phase 2: Compliance Enforcement

| Task File                          | Goal                                          | Status        | Next Action                         | ETA (days) | Dependency            |
|-----------------------------------|-----------------------------------------------|---------------|-------------------------------------|------------|-----------------------|
| `task-consent-enforcement.md`     | Enforce consent settings on all tags          | 🚧 In Progress | Begin tag updates in GTM            | 1–2        | Requires Cookiebot    |
| `task-server-container-audit.md`  | Audit server-side container `GTM-M7BMM8ZQ`    | 🚧 In Progress | Await vendor response or shut down  | 2          | Temple Advertising     |

---

## 🗂️ Phase 3: Analytics & Tag Accuracy

| Task File                          | Goal                                          | Status        | Next Action                         | ETA (days) | Dependency            |
|-----------------------------------|-----------------------------------------------|---------------|-------------------------------------|------------|-----------------------|
| `task-clarity-implementation.md`  | Implement Clarity via GTM                     | 🕒 Pending     | Tag test & publish post-consent     | 2          | Consent enforcement    |
| `task-crossdomain-tracking.md`   | Restore GA4 session continuity across domains | 🕒 Pending     | Deploy linker updates after consent | 2–3        | Consent enforcement    |
| `task-phase-out-ua.md`           | Remove deprecated UA tracking                 | 🕒 Pending     | Fully disable after GA4 validation  | 2–3        | GA4 validated          |

---

## 🧭 Status Key
- ✅ Complete – Task file fully documented and approved
- 🚧 In Progress – Implementation partially done
- 🕒 Pending – Awaiting dependency or stakeholder input
- ❌ Deprecated – Cancelled or replaced

---

## 📊 Reference: Tag Status Map

| File                  | Purpose                                       | Maintainer | Last Updated |
|-----------------------|-----------------------------------------------|------------|---------------|
| `tag-status-map.md`   | Tracks all GTM tags, consent config, and status | Assistant  | 2025-05-25    |

> This file supports `task-consent-enforcement.md`, `task-phase-out-ua.md`, `task-clarity-implementation.md`, and other tracking implementation work.  
> Use it to confirm individual tag gating, firing scope, and deprecation timing.

