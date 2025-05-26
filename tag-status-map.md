---
# 🧭 Tag Status Map – GTM-TGH83XK (Web Container)
> Project: `2505-DTA-GTM`
> Container ID: `GTM-TGH83XK`
> Version: 15 (Exported 2025-05-25)
> Scope: Tracks all tag visibility, consent status, and firing conditions

---

## 📌 Purpose
This document maps the **current state** of all tags within the GTM Web container, for audit, compliance, and debugging visibility. Tags are grouped by category with status indicators to support troubleshooting and consent validation workflows.

Legend:
- ✅ = Complete/Confirmed
- 🟡 = Pending Fix
- ❌ = Broken/Missing
- 🚫 = Deprecated/To Remove

---

## 📋 Tag Inventory

| # | Tag Name                                           | Type      | Consent | Firing Scope     | Notes |
|----|----------------------------------------------------|-----------|---------|------------------|-------|
| 1 | CU - Engage Timer                                  | HTML      | ❌      | 🟡 Not All Pages  | User idle engagement tracking |
| 2 | CU - YouTube Tracking                              | HTML      | ❌      | 🟡 Not All Pages  | Video tracking integration |
| 3 | GA - Event - Contact Link Clicks                   | UA        | ❌      | Partial          | Legacy Universal Analytics |
| 4 | GA - Event - Engaged Time                          | UA        | ❌      | Partial          | Tracks user activity time |
| 5 | GA - Event - File Download                         | UA        | ❌      | Partial          | PDF/XLS/DOC file clicks |
| 6 | GA - Event - Outbound Link Click                   | UA        | ❌      | Partial          | Offsite link tracking |
| 7 | GA - Event - YouTube Tracking                      | UA        | ❌      | Partial          | Redundant with Tag #2? |
| 8 | GA - Events - Scroll                               | UA        | ❌      | Partial          | Scroll depth tracking |
| 9 | GA - Pageview - All Pages                          | UA        | ❌      | ✅ All Pages      | Legacy, non-consented |
| 11 | Pardot - Pageview - All pages                     | HTML      | ❌      | ✅ All Pages      | Pardot legacy tracker |
| 12 | Facebook - Base tracking - All pages              | HTML      | ❌      | ✅ All Pages      | Uses Pixel ID `1062378757459509` |
| 14 | Facebook - Pageview - All pages                   | HTML      | ❌      | ✅ All Pages      | Secondary Pixel call |
| 28 | Cookiebot CMP                                     | Custom    | ❌      | ❌ Misconfigured  | CMP not enforcing consent |
| 29 | GA4 Configuration - G-BRXZCXMZP5                  | GA4       | ❌      | ✅ All Pages      | Missing linker domains |
| 30 | Conversion Linker                                 | Google    | ❌      | ✅ All Pages      | Cross-domain passthrough unset |
| 31 | Google Ads Conversion Tracking                    | Google Ads| ❌      | ✅ All Pages      | No enhanced conversion |
| 42 | FB_CONVERSIONS_API...GA4_Config                   | GA4       | ❌      | Partial          | CAPI transport tag |
| 43 | FB_CONVERSIONS_API...GA4_Event                    | GA4 Event | ❌      | Partial          | Classy donation events |
| 44 | FB_CONVERSIONS_API...Pixel_Event                  | HTML      | ❌      | Partial          | Pixel donation events |
| 45 | FB_CONVERSIONS_API...Pixel_Setup                  | HTML      | ❌      | Partial          | Pixel setup (with nonce) |
| 135 | GA4 Event - Classy Transaction Completion        | GA4 Event | ❌      | Classy only       | Custom parameters set |
| 136 | Facebook Event - Classy Donation                 | HTML      | ❌      | Classy only       | Pixel donation event |
| 137 | Facebook Event - Classy Registration             | HTML      | ❌      | Classy only       | Pixel registration event |
| 138 | Microsoft Clarity - Official                     | HTML      | ❌      | ✅ All Pages      | Heatmap, session replay |

---

## ✅ Follow-ups

- [ ] Enforce consent on **all tags** via `consentSettings` → `GRANTED`
- [ ] Validate Clarity firing via debugger tools
- [ ] Consider deprecating **UA tags** (tags #3–#9)
- [ ] Validate `linker_domains` for Tag #29 (GA4 config)
- [ ] Set consistent naming conventions

---

## 🔄 Related Files
- `GTM-TGH83XK_v15-original.json` (source container export)
- `task-consent-enforcement.md`
- `task-crossdomain-tracking.md`
- `task-clarity-implementation.md`
