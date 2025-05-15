
# 🧠 Project Memory: GTM Tracking Reset for SFZC.org
**Filename:** `2505-dta-gtm-updates-troubleshooting.md`  
**Project Code:** 2505-DTA-GTM-UPDATES  
**Last Updated:** 2025-05-14  

---

## 🔁 Reset Overview (May 2025)

This is a formal reset of the Google Tag Manager (GTM) tracking implementation on SFZC.org. The system was previously modified by outside contractors, but:

- The names of those contractors and their goals are **unknown**
- The current GTM container has **undocumented tags and logic**
- There is no clear record of what tracking was expected or what is actively working

### 🎯 Reset Goals

- Rebuild visibility and documentation
- Confirm what’s firing and whether it's compliant
- Clarify roles and decision authority
- Implement GA4, Microsoft Clarity, and consent compliance from a known baseline

### 👥 Roles & Context

| Role                     | Name               | Notes |
|--------------------------|--------------------|-------|
| Lead Implementer         | Greg Bilke         | New to GTM; rebuilding from unknown state |
| Analytics Sponsor        | Dan Belsky         | IT Director; worked with prior contractors |
| Contractor History       | Unknown            | Names, implementations, and intent unclear |

---


# 🧠 Project Memory: GTM Tracking Updates on SFZC.org  
**Filename:** `2505-dta-gtm-updates-troubleshooting.md`  
**Project Code:** 2505-DTA-GTM-UPDATES  
**Last Updated:** 2025-05-14  

---

## 🔍 Project Overview
This project combines and manages tracking diagnostics and tag implementations for SFZC.org. It unifies three key task areas:

- Microsoft Clarity Integration via GTM
- Classy Donation Tracking (GA4 Ecommerce Events)
- **GTM Health Check & Cookiebot Compliance Review** (New)

All work is scoped within the existing Google Tag Manager (GTM) setup on [SFZC.org](https://sfzc.org), and includes testing, debugging, and implementation across GA4, Clarity, and third-party consent tooling.

---

## 👤 Roles & Responsibilities

| Role                     | Name                     | Contact                     |
|--------------------------|--------------------------|-----------------------------|
| Lead Implementer         | Greg Bilke               | webcoordinator@sfzc.org     |
| Analytics Owner / Sponsor | Dan Belsky              | dan.belsky@sfzc.org         |
| External Support         | Zoey Brown (Community Boost) | zoey@communityboost.org |

---

## 🧭 Task Areas Under This Project

### 🟦 Task: Classy → GA4 Ecommerce Tracking  
**Former File:** `2505-gta-classy-gtm-memory.md`

#### ✅ Known Issues Addressed
- Replaced GA4 event param `amount` → `value`
- Removed duplicate GA4 Config tag

#### 🧪 Diagnostic Findings
- GA4 events blocked on both `sfzc.org` and Classy subdomain
- Four Facebook Conversions API (CAPI) tags suspected to conflict with GA4
- Disabling CAPI temporarily allowed GA4 `purchase` to fire

#### ❓ Open Questions
- Are FB CAPI tags still required? → *Pending Dan’s input*
- Who implemented the original server-side tagging logic?
- Broader GA4 tracking (beyond ecommerce) affected?

#### 📋 Next Steps
- [ ] Confirm FB CAPI tag requirement
- [ ] Temporarily pause CAPI tags to confirm GA4 flow
- [ ] Validate broader GA4 tracking events
- [ ] Review network/server logs for GA4 block patterns

---

### 🟩 Task: Microsoft Clarity Setup via GTM  
**Former File:** `2505-dta-Clarity-heatmaps-memory.md`

#### 🔧 Setup Requirements
- Script installed via GTM Custom HTML tag
- Must load in the `<head>` of every page (Microsoft best practice)
- Initially fire only on test page, then expand to All Pages

#### 📄 Verified Configuration
- Clarity Project ID: `rfyzkzgfcs`
- Source: Email from Microsoft Clarity → shared via Dan Belsky

```html
<script type="text/javascript">
    (function(c,l,a,r,i,t,y){
        c[a]=c[a]||function(){(c[a].q=c[a].q||[]).push(arguments)};
        t=l.createElement(r);t.async=1;t.src="https://www.clarity.ms/tag/"+i;
        y=l.getElementsByTagName(r)[0];y.parentNode.insertBefore(t,y);
    })(window, document, "clarity", "script", "rfyzkzgfcs");
</script>
```

- Clarity Dashboard: https://clarity.microsoft.com/projects/view/rfyzkzgfcs/dashboard?date=Last%203%20days
- Setup Docs: https://learn.microsoft.com/en-us/clarity/third-party-integrations/google-tag-manager

#### 🧪 Testing Strategy
| Step | Description | Status |
|------|-------------|--------|
| ✅ | Obtain Clarity script | Done |
| ⬜ | Create GTM **Custom HTML tag** | Next |
| ⬜ | Assign **test-only trigger** (`Page Path contains /test-page`) | Planned |
| ⬜ | Confirm `<head>` injection and verify with DevTools | Pending |
| ⬜ | Validate GTM tag in Preview mode | Pending |
| ⬜ | Confirm data appears in Clarity dashboard | Pending |
| ⬜ | Expand trigger to fire on All Pages | Pending |

#### 📌 Notes from Dan Belsky
- Clarity may already be receiving traffic via previous GA integration
- No urgency; confirmed data flow visible in dashboard
- Clarified options in Clarity’s setup panel are unclear; we chose GTM install per best practices

#### 🔠 Tag Naming Recommendation
- Initial tag: `Clarity - Load Script - HEAD - Test`
- Final production: `Clarity - Load Script - HEAD - All Pages`

---

### 🟨 Task: GTM Health Check & Cookiebot Compliance Review  
**Added:** 2025-05-14

#### 📌 Context
- Raised by: Dan Belsky, via feedback from Community Boost (see Cookiebot email)
- Concern: GTM may not be properly configured to respect Cookiebot banner consent. Some tags (e.g., FB Pixel) are firing without being gated.
- Relevance: SFZC.org’s compliance with GDPR/CCPA depends on properly handling marketing & analytics tracking based on consent.

#### 📂 Source Document
- Email: `sfzc.org Mail - Checking on Cookiebot.pdf`

#### 🛠️ Goals
- Conduct full GTM container audit for tag integrity and consent gating
- Verify whether Google Consent Mode is active and tags are compliant
- Identify & fix GTM misconfigurations

#### 🧪 Diagnostic Focus Areas
| Area | Purpose |
|------|---------|
| Cookiebot Consent Mode | Ensure Consent API wired to GTM |
| GA4 Tags | Respecting analytics consent? |
| Facebook Pixel | Blocked or firing early? |
| Classy API | Server-side tagging bypassing consent? |
| Tag Timing & Load | Detect misfiring or incorrect scope |
| Legacy Tags | Identify unmaintained/inactive scripts |

#### 🧰 Recommended Tools
| Tool | Use Case |
|------|----------|
| GTM Preview Mode | Simulate and inspect tag firing |
| Omnibug | Inspect live network requests and consent values |
| Google Tag Assistant | GA4 validator |
| Cookiebot Debugger | Show consent categories granted/denied |
| GA4 DebugView | Track event firing live |
| Clarity Dashboard | Confirm that traffic/session replay is working |

#### 💻 Environment Notes
- GTM in `<head>` across SFZC.org
- Cookiebot is active but integration status with GTM unknown
- Clarity integration underway
- User setup: macOS, Chrome, DevTools

#### 📋 Next Steps
- [ ] Export current GTM container
- [ ] Audit tags and consent settings via Omnibug
- [ ] Review GTM Preview firing rules
- [ ] Cross-reference Cookiebot consent state vs tag behavior

---

## 🧠 Tools Spotlight: Omnibug  
**Type**: Browser Extension (Chrome, Firefox)  
**Purpose**: Debug analytics and tag data  
**URL**: [Omnibug for Chrome](https://chrome.google.com/webstore/detail/omnibug/jnkmfdileelhofjcijamephohjechhna)

#### 🔍 Features
- Shows decoded tracking payloads from GA4, FB Pixel, Clarity, Classy, etc.
- Displays consent values
- Helps verify tag behavior and blocking on user consent
- Great for before/after comparisons on consent interactions

---

## 📎 Historical Notes

The contents of the following documents are now fully integrated into this file as structured tasks:
- `2505-gta-classy-gtm-memory.md`
- `2505-dta-Clarity-heatmaps-memory.md`
- `sfzc.org Mail - Checking on Cookiebot.pdf`

This file is the canonical working memory.

---

## 📌 Change Log

| Date       | Update Summary                                      | By          |
|------------|------------------------------------------------------|--------------|
| 2025-05-14 | Initial merged memory created from two task threads | Greg Bilke   |
| 2025-05-14 | Verified Clarity tracking code and implementation plan added | Assistant   |
| 2025-05-14 | Added GTM Health Check task and Cookiebot concern | Assistant   |
