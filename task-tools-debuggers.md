---
# 📌 Task: Tools and Debuggers for GTM Validation
> 📎 References: `auth.md` (canonical authority for GTM project)
---

## 🎯 Goal
Document and consistently use the recommended tools for validating GTM tag configuration, consent behavior, and analytics output.

---

## 🛠️ Recommended Tools

### 🔍 Tag Debugging
| Tool                         | Purpose                                                 |
|------------------------------|---------------------------------------------------------|
| Google Tag Assistant (Preview Mode) | Visualize GTM tag firing behavior and setup       |
| Google Consent Mode Debugger | Validate consent states and enforcement                 |
| Omnibug                      | Inspect outbound analytics and tracking requests        |

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
| 2025-05-18 | Task doc created               | Assistant  |
