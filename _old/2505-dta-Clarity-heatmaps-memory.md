# 🧠 Project Memory: Microsoft Clarity on SFZC.org  
**Filename:** `2505-dta-Clarity-heatmaps-memory.md`  
**Project:** Implement Microsoft Clarity via GTM for SFZC.org  
**Last Updated:** 2025-05-12  

---

## 🔧 Environment Overview

- **Site:** [SFZC.org](https://www.sfzc.org)
- **CMS:** Drupal
- **Hosting Platform:** Pantheon
- **Tag Manager:** Google Tag Manager (GTM), deployed in `<head>`
- **Clarity Status:** Not yet implemented as of 2025-05-12

---

## 👤 Roles

- **Lead Implementer:** Greg Bilke (`webcoordinator@sfzc.org`)
- **Clarity Project Owner:** Dan Belsky (`dan.belsky@sfzc.org`)
  - Will provide Clarity tracking code
- **Project Type:** Tracking Integration / Heatmap & Session Replay

---

## 🪪 Integration Details

- **Tracking Tool:** Microsoft Clarity
- **Integration Method:** Via GTM (Custom HTML tag in `<head>`)
- **Target Pages:** Site-wide (All Pages trigger)

---

## 🧪 To-Do Checklist

- [ ] Receive Clarity project code snippet from Dan
- [ ] Create GTM Custom HTML tag with Clarity script
- [ ] Set GTM trigger to **All Pages**
- [ ] Confirm tag fires **in HEAD** (already managed by GTM config)
- [ ] Use browser console + Network tab to verify Clarity loads
- [ ] Confirm Clarity dashboard shows data from live traffic
- [ ] Document tag name and configuration for audit trail

---

## 🧰 Testing Tools

- **Browser DevTools:** Confirm network call to `clarity.ms`
- **Microsoft Clarity Dashboard:** Validate session traffic
- **GTM Preview Mode:** Ensure tag fires on page load

---

## 🗂️ Reference Links

- Clarity Project: https://clarity.microsoft.com/projects/view/rfyzkzgfcs/dashboard?date=Last%203%20days
- Clarity Setup: https://clarity.microsoft.com/projects/view/rfyzkzgfcs/settings#setup
- Clarity Getting Started: https://clarity.microsoft.com/projects/view/rfyzkzgfcs/gettingstarted

---

