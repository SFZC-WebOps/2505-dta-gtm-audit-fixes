# ✅ GTM Implementation Cross-Check Report  
**Project:** 2505-DTA-GTM-Audit-Fixes  
**Scope:** SFZC Web Tagging (GTM Container `GTM-TGH83XK`)  
**Last Updated:** 2025-05-21  
**Author:** ChatGPT Technical Assistant  
**Maintainer:** Greg Bilke (greg.bilke@sfzc.org)  
**Canonical Source:** `auth.md`

---

## 🔍 Executive Summary

This report outlines the current audit findings, known issues, tasks in progress, and required remediation across SFZC’s GTM tracking infrastructure. Each item is tied to a scoped task file in the Git project and backed by container version `v15` (exported May 16, 2025). Reviewers can trace all proposed and completed changes via the task files and container JSON export.

---

## 📋 Active Issues and Planned Fixes

| Issue | Status | Task File | Summary |
|-------|--------|-----------|---------|
| ❌ UA tags still active | Not started | `task-phase-out-ua.md` | `UA-1720237-1` tags remain in GTM. These are deprecated and must be replaced with GA4 equivalents. |
| ❌ Consent settings not enforced | Not started | `task-consent-enforcement.md` | All 24 tags lack `consentSettings`. Cookiebot is present but not linked to tag firing. |
| ⚠️ Server container undocumented | In review | `task-server-container-audit.md` | View-only container `GTM-M7BMM8ZQ` sends Facebook CAPI events without consent controls or owner documentation. |
| ❌ Missing GA4 linker config | Not started | `task-crossdomain-tracking.md` | GA4 tag is not configured with `linker_domains`. Breaks cross-domain session continuity (`give.sfzc.org`, `forms.sfzc.org`). |
| ⚠️ Clarity tag incomplete | Not started | `task-clarity-implementation.md` | Clarity tag exists but does not fire on all pages and lacks consent enforcement. Needs reconfiguration and validation. |

---

## 🔧 Tools Used for Audit & Validation

| Tool | Purpose |
|------|---------|
| **GTM Preview Mode** | Validate tag firing in controlled environments |
| **Consent Mode Debugger** | Confirm tags respect Cookiebot settings |
| **Omnibug** | Monitor outbound analytics requests |
| **GA4 DebugView** | Ensure proper event structure and parameter mapping |

All validation tools and usage practices are documented in `task-tools-debuggers.md`.

---

## ✅ Remediation Tasks (Summary by File)

### `task-phase-out-ua.md`
- UA ID `UA-1720237-1` must be removed.
- Tags migrated to GA4 event structures.
- DebugView required for validation.

### `task-consent-enforcement.md`
- All tags updated with `consentSettings`.
- Consent types matched to purpose (`ad_storage`, `analytics_storage`).
- Cookiebot must fire early and gate all behavior.

### `task-server-container-audit.md`
- Server-side GTM `GTM-M7BMM8ZQ` sends Facebook CAPI events without consent.
- No known owner; access is view-only.
- Recommendation: disable unless vendor confirms continued use.

### `task-clarity-implementation.md`
- Rebuild Clarity tag using ID `rfyzkzgfcs`.
- Test on `/test-page` first.
- Enforce consent and switch to `All Pages` once validated.

---

## ⚠️ Key Risks and Dependencies

| Risk | Description |
|------|-------------|
| ❌ GDPR/CCPA Violation | Tags may fire before user consent. Cookiebot not fully enforced. |
| ❌ Data Gaps | Some pages not tagged or improperly tracked due to trigger misconfigurations. |
| ⚠️ Ownership Risk | Server container (`GTM-M7BMM8ZQ`) is orphaned. No access or audit trail. |
| ⚠️ Redundant Tracking | Facebook Pixel duplicated across Web and Server containers (ID: `1062378757459509`). |
| ⚠️ Consent Mode Misuse | GA4 and Clarity tags not currently respecting Cookiebot status. |
| ⚠️ Measurement Integrity | No cross-domain tracking for donation-related domains. Breaks user journey data continuity. |

---

## 🧭 Reviewer Instructions

To validate our progress:
1. Refer to `auth.md` for the canonical summary of container state and stakeholders.
2. Open each `task-*.md` file for implementation details, fix plans, and validation checklists.
3. Use GTM Preview and Consent Mode Debugger to validate behavior in your environment.
4. Cross-reference GTM container version `v15` (`GTM-TGH83XK_v15.json`) for technical alignment.

---

## ✅ Are We Overlooking Anything?

> From the assistant’s review, the following additional considerations may improve reliability or clarity:

- **GA4 Custom Dimensions**: Ensure any GA4 events being added have matching custom dimensions configured in GA4 Admin → Custom Definitions.
- **Container Version Control**: Consider adopting Git-based tagging for container exports (e.g., `v15-initial-audit`, `v16-consent-update`).
- **Tag Documentation**: Add in-GTM tag notes and GTM Workspaces for staging/test/live separation.
- **Access Review**: Periodically audit users and permissions on GTM accounts for both Web and Server containers.
- **Redundancy Checks**: Verify that Clarity, GA4, and FB tags don’t double-fire on event pages.
