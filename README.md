# 📊 GTM Tracking Audit & Fixes: SFZC.org

**Project Code:** 2505-DTA-GTM-AUDIT-FIXES  
**Repo Role:** Central hub for structured GTM audit remediation, modular documentation, and implementation task management for SFZC.org

---

## 🧠 Overview

This project addresses analytics misconfiguration, tag governance, and consent enforcement for the [SFZC.org](https://www.sfzc.org) website, which runs on Drupal and uses Google Tag Manager (GTM) for tag delivery in the `<head>`.

---

## 🔐 Canonical Project Source

- **`auth.md`** — Authoritative record for all GTM container IDs, platform IDs, ownership details, and cross-system linkages.  
  Treat this file as the **source of truth** across all task files.

---

## 📋 Modular Task Files

Each of the following documents addresses a discrete fix or audit requirement:

| Filename                              | Purpose |
|---------------------------------------|---------|
| `task-fix-all-pages-trigger.md`       | Ensure all base tags fire site-wide |
| `task-consent-enforcement.md`         | Enforce cookie consent across all tags |
| `task-crossdomain-tracking.md`        | Implement cross-domain GA4 session continuity |
| `task-phase-out-ua.md`                | Remove deprecated Universal Analytics tracking |
| `task-folder-tagstructure-cleanup.md` | Normalize tag names, folders, and load order |
| `task-server-container-audit.md`      | Audit and validate use of server-side GTM |
| `task-tools-debuggers.md`             | List tools for testing, validation, and consent debugging |

---

## 🧾 Historical Files

- `_old/2505-dta-gtm-updates-troubleshooting-memory.md` — Initial working memory file used during audit phase.  
  Now archived and replaced by modular task system.

- `2505-gta-classy-gtm-memory.md`, `2505-dta-Clarity-heatmaps-memory.md` — Previously integrated into audit threads. Retired.

---

## 👥 Team & Contacts

- **Lead:** Greg Bilke (`webcoordinator@sfzc.org`)
- **Sponsor:** Dan Belsky (`dan.belsky@sfzc.org`)
- **Legacy Contractor:** Temple Advertising

---

## 🔖 Git & Tagging Conventions

- Commits follow modular task descriptions
- Tags use the format: `vX.X-task-description`
- Latest milestone: **[`v1.1-task-modularization`](https://github.com/SFZC-WebOps/2505-dta-gtm-audit-fixes/releases/tag/v1.1-task-modularization)**

---

## ✅ Repo Usage Notes

- All source facts belong in `auth.md`
- All implementation logic lives in `task-*.md` files
- Use GitHub and GTM Preview tools to validate each implementation

---
