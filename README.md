# Create a README.md file for the project
readme_content = """# 📊 GTM Tracking Updates: SFZC.org

**Project Code:** 2505-DTA-GTM-UPDATES  
**Repo Role:** Central hub for analytics tag troubleshooting, documentation, and implementation related to SFZC.org

---

## 🧠 Overview

This project consolidates multiple analytics-related tasks under a single memory and documentation framework. It brings together:

- GA4 Ecommerce Tracking fixes for Classy donation events
- Microsoft Clarity implementation via Google Tag Manager (GTM)

All work supports the Drupal-based [SFZC.org](https://www.sfzc.org) website and is managed using GTM in the `<head>` section.

---

## 🗂️ Project Components

### 1. `2505-dta-gtm-updates-troubleshooting.md`
Primary memory file for the project. Combines technical details, task lists, diagnostics, and known issues for both Clarity and Classy/GA4 workflows.

### 2. Task Areas
- **Classy → GA4 Ecommerce Tracking**
- **Microsoft Clarity Integration**

See memory file for full context and status.

---

## 👥 Team & Contacts

- **Lead:** Greg Bilke (`webcoordinator@sfzc.org`)
- **Sponsor:** Dan Belsky (`dan.belsky@sfzc.org`)
- **Vendor Support:** Community Boost

---

## 📎 Related Docs (Archived & Integrated)
- `2505-gta-classy-gtm-memory.md`
- `2505-dta-Clarity-heatmaps-memory.md`

These documents were integrated into the main memory file and no longer need to be updated separately.

---

## 🔖 Naming Convention

Follows internal SFZC WebOps naming structure:

- `YYMM-ORG-Title` (e.g., `2505-dta-gtm-updates`)
- ORG codes:  
  - `DTA` = Data Tracking & Analytics  
  - `CMS` = Content Management Systems  
  - `DAM` = Digital Asset Management  

---

## ✅ Repo Usage Notes

- All tasks should be reflected in the memory file.
- Use Git commits to track changes to `2505-dta-gtm-updates-troubleshooting.md`.
- For deployment-specific GTM configuration, see browser DevTools and GTM Preview Mode for testing.

---

"""

readme_path = "/mnt/data/README.md"
with open(readme_path, "w") as f:
    f.write(readme_content)

readme_path
