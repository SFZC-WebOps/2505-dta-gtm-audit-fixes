**📄 GTM Tracking Reset: Questions for Dan Belsky (May 2025\)**  
 **Prepared by:** Greg Bilke  
 **Role:** Web Operations, SFZC  
 **For:** Dan Belsky, IT Director, SFZC

---

### **🎯 Purpose**

We are resetting the GTM (Google Tag Manager) tracking project to better understand the current state, past decisions, and future goals.

I’m still **new to GTM**, and from our conversations, I understand that you’ve worked with **several contractors** to try to move data from GTM into Google Analytics (GA).

At this point, I do **not know who those contractors were**, what they built, or what goals they were aiming to meet.  
 To move forward effectively — and to avoid rebuilding or breaking anything — I’d like to understand the **backstory** so we can make informed decisions.

This doc is a starting point for that conversation.

---

### **🧠 SECTION 1: BACKGROUND QUESTIONS**

1. **Contractor History**

   * **Who has worked with you (or SFZC staff) in GTM or GA in the past 2–3 years?**   
     1. Belen Molinary (contractor with Temple Media).   
     2. Dezhay Caraway & Zoey Brown (Contractors from Community Boost \- provided to us via Classy)

   * **Do you know what their main objectives were?**  
     1. Belen was setting up Facebook and Instagram (Meta) ads and trying to track referrals and traffic to [sfzc.org](http://sfzc.org) and sales made through Classy based on clicks on the Meta ads.   
     2. Community Boost was working on a similar thing as Belen \- in essence they were working together, to track conversions (sales made on the Classy platform based on clicks from Meta ads). We used the ‘Meta Conversions API’ (an integration provided by Classy) to do this. Community Boost was highly technical in getting this API to work.

   * **Were any tracking dashboards, reports, or integrations built?**  
     1. The ‘Meta Conversions API’ was turned on. [This link](https://developers.facebook.com/docs/marketing-api/conversions-api/) was provided from the Classy site to learn more about this integration.

        

2. **Tracking Goals**

   * **What were we hoping to learn or measure through GTM/GA?**    
      **(e.g., ecommerce, page traffic, form fills, campaign ROI?)**  
     1. To track conversions (sales made on the Classy platform based on clicks from Meta ads)

   * **Are there any metrics or reports that are critical to current operations?**  
     1. Facebook Business Analytics reports

3. **Decision-Making & Ownership**

   * **Who owns decisions about what gets tracked and how?**  
     1. Ultimately SFZC IT does (Greg Bilke and Dan Belsky)

   * **Are there any external stakeholders (marketing, finance, development) who expect specific data?**  
     1. Comms does expect Facebook Business Analytics reports to work for them (in their current form)

---

### **🧪 SECTION 2: CURRENT SYSTEM QUESTIONS**

4. **What’s Working / What’s Not**

   * **Is anything in GA currently “just working” — even if we’re not sure why?**  
     1. I am not sure about this in detail, but likely so\!

   * Have you noticed anything missing or inaccurate?  
     1. ?

5. **Consent & Privacy**

   * **Do you know if SFZC is actively managing cookie consent (GDPR/CCPA) through GTM?**  
     1. I believe so with Cookiebot

   * Was Cookiebot or Consent Mode discussed with any contractor?  
     1. Dezhay Caraway has mentioned in passing that Cookiebot may not be functioning as we’ve anticipated on our site. He simply noticed this by looking at GA settings I believe…

6. **Clarity / Other Tools**

   * **Has Microsoft Clarity or any other analytics tool been connected in the past?**  
     1. No  
   * **Do we expect Clarity or Facebook tracking to be active right now?**  
     1. Yes, definitely

---

### **🔧 SECTION 3: NEXT STEPS & RECOMMENDATIONS**

7. **Short-Term Approach**

   * **Are you okay with us building clarity and structure inside GTM — as long as we back up the current setup?**  
     1. Yes, as long as we cautiously approach this and ensure, most importantly, that the Meta Conversions API continues to function

   * **Would you prefer to review or approve any changes before they go live?**  
     1. Only if they could affect the Meta Conversions API functionality

8. **Collaboration**

   * **Would it be helpful to loop in a past contractor (if available)?**  
     1. It might be. I’m not sure if Community Boost would be available (contractually)

   * **Is there any documentation or account access you can share (e.g., GTM container exports, GA access)?**  
     1. I do not recall having this

---

### **✅ Final Note**

This reset isn’t about redoing everything — it’s about understanding what we have, deciding what we need, and moving forward with confidence.

I’ll organize anything we find into a clear project memory so we don’t lose this context again.

Let me know how you'd like to proceed.

