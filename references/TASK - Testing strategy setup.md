# 📌 Task: Testing Strategy Setup for GTM Validation
> 📎 References: `auth.md` (canonical authority for GTM project)  
> 🗂 Source File: `task-testing-strategy.md`  
> ⏳ ETA: 1–2 hours (can be done in a single work session)

---

## 🎯 Goal

Establish a safe, repeatable testing environment to validate Google Tag Manager changes before going live.

---

## 🔍 Problem Statement

- No staging mechanism exists for GTM validation
- Consent enforcement and Clarity tags must be tested before rollout
- Need `/test-page` route or equivalent isolated path to simulate live environment without risk

---

## 🛠️ Implementation Plan

### ✅ Step 1: Choose a Controlled Test Page

- Confirm that a route like `https://sfzc.org/test-page` is available (ask developer or create stub page if needed)
- If not possible, use GTM Environment or tag-level trigger condition:
  ```text
  Page URL contains /test-page
