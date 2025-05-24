# 📌 Task: Testing Strategy

> ✅ **Status:** Local testing infrastructure confirmed working. Ready for use in consent and Clarity validation.

> 📎 References: `auth.md` (canonical authority for GTM project)

---

## 🎯 Goal
Define environment and testing process for safe GTM changes

---

## 🔍 Problem Statement
- No staging mechanism currently in place for safe validation of tag edits
- Consent enforcement and Clarity implementation require controlled pre-launch testing

---

## 🛠️ Implementation Plan

### ✅ Step 1: Choose Controlled Test Environment
- Coordinate with Kalamuna on available Drupal staging/test environment
- If not available, use:
  - GTM environments, OR
  - Temporary trigger condition: `Page URL contains /test-page`

### ✅ Step 2: Configure Consent Mode and Observability
- Enable Consent Mode Debugger
- Use GA4 DebugView, GTM Preview, and Omnibug for tag validation
- Validate tag behavior in the presence and absence of Cookiebot acceptance

### ✅ Step 3: Define Exit Criteria
- All test tags show correct firing sequence in `/test-page`
- Tags respect `consentSettings` and don't fire prematurely
- GA4 and Clarity data confirm receipt post-consent

---

## 📋 Fix Checklist
- [ ] Testing route (`/test-page`) working and isolated
- [ ] Consent Mode Debugger used to validate gating
- [ ] GA4 DebugView confirms correct event structure
- [ ] Tag Assistant Preview used for all new tags
- [ ] Clarity Dashboard confirms tracking

------



## ✅ Implementation Session Log

### 🗓️ 2025-05-24 – GTM Testing Environment Successfully Configured

**Environment:**  
- Local: `http://localhost:8080`  

- Served via NGINX container using OrbStack/Docker  

- Host directory: `/Volumes/webops-work/SITES/gtm-test`  

- Docker run command used:
  ```bash
  docker run --rm --name gtm-test-nginx \
    -p 8080:80 \
    -v ~/Sites/gtm-test:/usr/share/nginx/html:ro \
    nginx
  ```

**Validation Results:**

- GTM container `GTM-TGH83XK` successfully connected via Tag Assistant
- Consent Mode events (`Consent Initialization`, `Consent Default`) confirmed firing
- `analytics_storage`, `ad_storage`, `functionality_storage` all defaulted to `denied`
- No analytics or tracking tags fired without consent
- No changes published to GTM or production environments

------



## 🔄 Change Log

| Date       | Change                                                       | By              |
| ---------- | ------------------------------------------------------------ | --------------- |
| 2025-05-18 | Task doc created                                             | Assistant       |
| 2025-05-21 | Expanded with GTM tools, `/test-page` strategy, and validators | Assistant       |
| 2025-05-24 | Added `Implementation Session Log`                           | Greg Bilke (GB) |
