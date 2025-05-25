# 📁 Consent Enforcement Task Directory

> This folder contains all working assets for implementing and validating consent enforcement in GTM container `GTM-TGH83XK` as part of the 2505-DTA-GTM project.

## 📌 Scope
Implements GDPR/CCPA-compliant consent gating using `consentSettings` and Cookiebot CMP integration across all tracking tags.  
Work follows the implementation plan in [`task-consent-enforcement.md`](../task-consent-enforcement.md) and must adhere to the production safeguard policy in [`auth.md`](../auth.md).

---

## 📂 Folder Structure

| Folder/File        | Purpose                                                                 |
|--------------------|-------------------------------------------------------------------------|
| `exports/`         | Original container exports before consent settings were applied         |
| `patches/`         | Cloned or modified tag configurations for consent testing               |
| `screenshots/`     | Evidence from GTM Preview, Consent Mode Debugger, GA4 DebugView         |
| `logs/`            | Optional Markdown logs of implementation sessions or validations        |
| `README.md`        | This file — explains purpose and structure                              |

---

## ✅ Process Checklist

- [ ] Export container before any changes
- [ ] Clone GA4 tag for `/test-page` with `consentSettings`
- [ ] Use GTM Preview Mode and Consent Debugger for validation
- [ ] Save validation screenshots and logs
- [ ] Do **not** publish to production until Drupal module is updated and testing is complete

---

## 🔒 Reference

- [auth.md](../auth.md) — Canonical source of truth (container IDs, compliance rules)
- [task-consent-enforcement.md](../task-consent-enforcement.md) — Implementation plan and session logs
- [ref-tools-debuggers.md](../ref-tools-debuggers.md) — Tooling reference

