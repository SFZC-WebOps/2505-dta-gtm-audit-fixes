---
# Reference: Tools and Debuggers for GTM Validation
> 📎 References: `auth.md` (canonical authority for GTM project)
---

---

## 🛠️ Recommended Tools

### 🔍 Tag Debugging
| Tool                         | Purpose                                                 |
|------------------------------|---------------------------------------------------------|
| Google Tag Assistant (Preview Mode) | Visualize GTM tag firing behavior and setup       |
| Google Consent Mode Debugger | Validate consent states and enforcement                 |
| Omnibug                      | Inspect outbound analytics and tracking requests        |

> ✅ All validation procedures used in the [Cross-Check Report (2025-05-21)](gtm-crosscheck-report-2025-05-21.md) align with the tools listed above. These tools form the standard baseline for verifying tag behavior, consent enforcement, and data accuracy.

> ℹ️ **Note on Microsoft Clarity:**
>  Clarity’s internal dashboard (https://clarity.microsoft.com) serves as a real-time validation environment for verifying tag installation and tracking behavior. Use it to confirm heatmap coverage, session recording presence, and script firing after consent is granted.

---

### 🧪 GTM Testing Methods
- Use GTM **Preview Mode** before publishing any changes
- Configure temporary triggers like `URL contains /test-page` for controlled validation
- Use **Consent Mode staging**:
```javascript
gtag('consent', 'default', {
  'ad_storage': 'denied',
  'analytics_storage': 'granted'
});
```
- Observe behavior before and after consent events (e.g., Cookiebot acceptance)

---

### 📦 GTM Management Practices
- Always export container versions to `.json` before publishing
- Maintain version control (e.g., label GTM versions clearly by date and purpose)
- Track publishing log alongside task files

---

## 📋 Usage Checklist
- [ ] Preview Mode tested on updated tags
- [ ] Consent Debugger confirms logic
- [ ] Events verified in GA4 Realtime / DebugView
- [ ] JSON export saved for current container version

---

## 🔄 Change Log
| Date       | Change                        | By         |
|------------|-------------------------------|------------|
| 2025-05-18 | Ref doc created             | Assistant  |
