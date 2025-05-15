# Google Tag Manager (GTM) Implementation at SFZC: Comprehensive Documentation

## 1. Implementation Overview & Technical Details

### GTM Container Information
- **Container ID:** GTM-TGH83XK (identified in Google's March 2025 notification)
- **Implementation Date:** Not explicitly documented, but has been in place for several years
- **Primary Implementation Architect:** Multiple contractors have worked on the implementation; specific names not documented
- **Current Access:** Managed by Greg Bilke (Web Operations Systems Manager) with possible access by Dan Belsky (IT Director)
- **Website Implementation:** 
  - Main website (sfzc.org) - Drupal-based implementation via Google Tag module
  - Blog site (blogs.sfzc.org) - WordPress-based implementation

### Current Technical Configuration
- **JavaScript Implementation:** Standard GTM container script embedded on all SFZC websites
- **Drupal Implementation:** Using the Google Tag module (versions affected by security vulnerabilities included <1.8.0 || >=2.0.0 <2.0.8)
- **WordPress Implementation:** Implementation method not explicitly documented, likely through theme integration or plugin
- **Tag Loading Sequence Issue:** According to Cookiebot reports, GTM is loading before Cookiebot consent is established, causing privacy compliance issues

### Identified Tags & Variables 
- **Google Analytics 4**
  - GA4 Configuration tag (duplicate found and removed in May 2025)
  - GA4 Event - Classy Transaction Completion tag
  - Parameter issue: Using "amount" instead of the required "value" parameter (identified and fixed by Community Boost)

- **Facebook/Meta Tags**
  - Facebook Pixel tags
  - Four Facebook Conversions API tags ("FB_CONVERSIONS_API tags")
  - These tags were identified as sending data server-side, which created conflicts with client-side tracking

- **Cookiebot Integration**
  - Reference to Cookiebot implementation, but specifics of the tags are not documented
  - Reports indicate integration is not functioning correctly for consent management

- **Classy Integration**
  - Classy transaction tracking tags for donation processing
  - Issues identified with GA4 event parameter naming

### Container Structure
- **Tag Organization:** Not explicitly documented
- **Trigger Configuration:** Multiple consent-based triggers required but appear to be improperly configured
- **Variables:** Limited documentation of variables; known to include transaction parameters

## 2. Organizational Context & Responsibility

### Role Responsibilities
Based on the Job Description documents, the Web Operations Systems Manager (Greg Bilke) is responsible for:

- **Analytics Suite Management:** Google Tag Manager, Google Analytics, Google Search Console
- **Privacy Management:** Cookiebot integration
- **Website Performance:** Monitoring, optimization, and reporting
- **Security:** Implementing and maintaining security protocols

From the "Web Operations System Manager - SFZC Job Description - Employee - August 2023" document:
> Analytics (Google Analytics, Google Search Console, and Google Tag Manager)

### Key Stakeholders
- **Greg Bilke:** Web Operations Systems Manager, primary implementer of GTM
- **Dan Belsky:** Operations and IT Director, has worked with contractors on GTM/GA implementations
- **External Contractors:** Various contractors have worked on the implementation (names not documented)

### Organizational Goals for GTM/Analytics
Based on the questions in the "GTM Tracking Reset" document, the organization aims to use GTM/GA for:
- Ecommerce tracking (Classy donations)
- Page traffic analysis
- Form fill monitoring
- Campaign ROI tracking

## 3. Current Issues & Challenges

### Technical Issues
1. **Cookiebot Integration Issues**
   - Monthly scan reports consistently show: "Some scripts may be loaded through Google Tag Manager before consent has been submitted"
   - GTM is not properly respecting Cookiebot consent values before firing tags
   - This creates privacy compliance risks

2. **Classy Transaction Tracking Problems**
   - Community Boost identified in May 2025:
     - The "GA4 Event - Classy Transaction Completion" tag was using incorrect parameter "amount" instead of "value"
     - A duplicate GA4 Configuration tag was found and removed
     - Events on Classy subdomain being blocked due to GA4 requests being rejected

3. **Tag Conflicts**
   - Facebook Conversions API tags (sending data server-side) conflicting with client-side tracking
   - Community Boost's testing showed that pausing FB_CONVERSIONS_API tags resolved some issues

### Security Vulnerabilities
1. **Google Tag Module Security Issues (Jan 2025)**
   - Affected versions: <1.8.0 || >=2.0.0 <2.0.8
   - Vulnerabilities: Cross Site Request Forgery (CSRF) and Cross Site Scripting (XSS)
   - Technical details:
     - "The module doesn't have the 'restrict access' flag on the 'administer google_tag_container' permission"
     - "The module doesn't sufficiently validate the enabling or disabling of a tag container"

2. **Cookiebot + GTM Module Security Issue (Oct 2024)**
   - Affected versions: <1.0.18
   - Vulnerability: Persistent Cross Site Scripting (XSS)
   - Technical detail: "The module doesn't sufficiently filter for malicious script"

3. **Tarte au Citron Module Security Issue (Nov 2024)**
   - Affected versions: <2.0.5
   - Vulnerability: Cross Site Scripting when GTM service is enabled
   - Technical detail: "When Google Tag Manager (GTM) service is enabled, an attacker can load a GTM container that completely changes the page or inserts malicious JS"

### Knowledge & Documentation Gaps
From the "GTM Tracking Reset" document (May 2025):
- Self-identified knowledge gap: "I'm still new to GTM"
- Lack of documentation about previous work: "I do not know who those contractors were, what they built, or what goals they were aiming to meet"
- Uncertainty about current tracking goals: "What were we hoping to learn or measure through GTM/GA?"
- Unclear ownership: "Who owns decisions about what gets tracked and how?"

From email in March 2025:
- "To be honest, GTM is not my strong point. I pretty much configure tags according to the default instructions and check that they are operational. I have not really spent a lot of time optimizing those tags as that is its own field of expertise."

## 4. Third-Party Integrations & Contractors

### Community Boost
- **Engagement Context:** Engaged through Classy to assist with Facebook Ads integration
- **Contact:** Zoey Brown (Associate Digital Specialist, Data Intelligence)
- **Work Performed:** 
  - Identified and resolved issues with Classy transaction tracking in GA4
  - Made container modifications:
    - Updated parameter from "amount" to "value" in GA4 Event tag
    - Removed duplicate GA4 Configuration tag
    - Identified conflicts with Facebook Conversions API
  - Testing methodology: "Temporarily paused [FB Conversions API tags] and tested a donation again"

### Kalamuna
- **Engagement Context:** Web development agency managing the Drupal site
- **Work Related to GTM:**
  - Recommended using GTM to implement SiteImprove script (Dec 2024)
  - Quoted 1-2 hours for Google Tag module security updates (Jan 2025)
  - Manages updates for Google Tag module in Drupal

### Cookiebot
- **Service Provider:** Privacy consent management platform from Usercentrics A/S
- **Integration Issues:** 
  - Monthly scan reports indicate GTM not respecting consent
  - Recommendation: "Make sure your GTM is set up to use Cookiebot consent values before loading tags that may set cookies"
  - Suggested resource: "See our GTM installation guide here"

## 5. Upcoming Changes & Recent Updates

### Google's Announced Changes (March 2025)
- **Effective Date:** April 10, 2025
- **Change Details:** Containers with Google Ads and Floodlight tags will automatically load a Google tag first, before sending events
- **Implementation Default:** "If you take no action, this update will happen automatically"
- **Technical Benefits:**
  - "One-click access to features: Turn on Enhanced Conversions, Cross-domain tracking, and Autoevents"
  - "Smoother data collection: If you've agreed to our Customer Data Terms of Service, we'll automatically enable 'User Provided Data' collection"

### Classy Analytics Update (November 2024)
- **Google Analytics 4 and Google Tag Manager Integration Updates:**
  - New variables, triggers, conversion events
  - Import template for Google Tag Manager
  - Support for Tealium for extended analytics
- **Meta Integration Features:**
  - One-click sharing to Instagram and Facebook
  - Dynamic posts and seamless checkout
  - Option to disable progress metrics in social posts
  - A/B testing for Facebook posts

### Security Updates Required
- Google Tag module to version 8.x-1.8 or 2.0.8 (depending on Drupal version)
- Cookiebot + GTM module to version 1.0.18 if in use
- Tarte au Citron module to version 2.0.5 if in use

## 6. Baseline Assessment & Reset Initiative

### Current Assessment (May 2025)
From the "GTM Tracking Reset" document:
- A reset project has been initiated to better understand the current state, past decisions, and future goals
- The document poses several key questions to build baseline knowledge:
  - Who has worked with GTM/GA in the past 2-3 years?
  - What metrics or reports are critical to current operations?
  - Who owns decisions about tracking?
  - Is anything in GA currently working properly?
  - How is cookie consent being managed?
  - Are other tools like Microsoft Clarity or Facebook tracking active?

### Strategic Importance
From the "Strategic Value Assessment" document (January 2025):
- The Web Operations Systems Manager position is described as providing "critical technical leadership" including analytics management
- The role delivers "comprehensive digital infrastructure management at $74,240 annually versus $168,000+ for contracted services"
- Analytics is mentioned as part of the evolution of web operations technologies: "Analytics and User Experience"

From the "Dharma Talk Archive Platform Options" document (February 2025):
- Original vision included "Advanced analytics and user engagement tracking" for the Drupal/JWP platforms
- Current challenge noted: "Our team doesn't have the resources to tap into those advanced capabilities"
- Reference to "We're paying $12,000 annually for a powerful system we're barely using"

## 7. Technical Details of Website Infrastructure

### Content Management Systems
- **Drupal (sfzc.org)**
  - Hosting: Pantheon
  - Analytics integration via Google Tag module
  - Security issues identified with Google Tag module

- **WordPress (blogs.sfzc.org)**
  - Hosting: DreamHost
  - Implementation method not explicitly documented

### Related Technical Infrastructure
- **Media Hosting:** JW Player ($12,000 annual cost)
- **Caching:** Redis
- **Content Delivery Network:** AGCDN
- **Security:** SSL, Cloudflare
- **Privacy Management:** Cookiebot

## 8. Specific Tag Configuration Details

### GA4 Event - Classy Transaction Completion Tag
- **Issue identified:** Using parameter "amount" instead of "value" required by GA4
- **Correction made:** Parameter updated to "value" by Community Boost
- **Impact:** This change was necessary for proper tracking in GA4 ecommerce reports

### Facebook Conversions API Tags
- **Quantity:** Four FB_CONVERSIONS_API tags identified
- **Issue:** Tags sending data server-side, causing conflicts with client-side tracking
- **Recommendation:** Community Boost suggested "pausing or deleting the FB_CONVERSIONS_API tags if they are no longer in use"
- **Testing result:** When these tags were paused, "the event was successfully sent to GA4"

### GA4 Configuration Tag
- **Issue:** Duplicate GA4 Configuration tag discovered
- **Action:** Duplicate tag removed by Community Boost
- **Impact:** Removing duplicate configuration improved data consistency

## 9. Action Items & Recommendations

Based on all gathered information, these are the documented technical recommendations:

### Immediate Technical Fixes
1. **Cookiebot Integration**
   - Ensure Cookiebot script loads before GTM
   - Configure GTM to properly respect Cookiebot consent values
   - Follow Cookiebot's GTM installation guide
   - Consider implementing "autoblocking mode" mentioned in Cookiebot reports

2. **Classy Transaction Tracking**
   - Address FB_CONVERSIONS_API tags per Community Boost's recommendation:
     ```
     "Pause or delete the FB_CONVERSIONS_API tags if they are no longer in use. 
     If those tags are still needed, we can explore potential workarounds."
     ```
   - Verify that parameter renaming from "amount" to "value" was properly implemented

3. **Security Updates**
   - Update Google Tag module to version 8.x-1.8 or 2.0.8 depending on Drupal version
   - Update Cookiebot + GTM module to version 1.0.18 if in use
   - Update Tarte au Citron module to version 2.0.5 if in use

### Knowledge & Documentation Needs
1. **Container Documentation**
   - Create inventory of all existing tags, triggers, and variables
   - Document tag firing conditions, particularly consent-related triggers
   - Map dependencies between tags
   - Create technical architecture diagram

2. **Process Development**
   - Implement change management process for GTM updates
   - Create testing workflow for tag modifications
   - Establish consent compliance audit process

## 10. Email Documentation Details

### Cookiebot Compliance Issues
Monthly scan reports consistently reported:
- "Some scripts may be loaded through Google Tag Manager before consent has been submitted"
- "Make sure your GTM is set up to use Cookiebot consent values before loading tags that may set cookies"
- "See our GTM installation guide here"

These reports were received for both domains (sfzc.org and blogs.sfzc.org) from September 2024 through May 2025.

### Community Boost Technical Findings (May 2025)
From email dated May 9, 2025:
> "We first reviewed the configuration of the 'GA4 Event - Classy Transaction Completion' tag and found that it was using the event parameter *amount*, which GA4 does not recognize by default. We updated the parameter to *value*, which GA4 recognizes and requires to properly display revenue in the ecommerce report. Additionally, we noticed a duplicate GA4 Configuration tag and removed it."

> "After making these updates and testing a couple of donations, we noticed that the purchase event still wasn't firing in GA4. We checked the browser console and saw that many events on the Classy subdomain are being blocked, as GA4 requests are being rejected by the server."

> "We also noticed there are four Facebook Conversions API tags in the GTM container. Since those tags send data server-side, we temporarily paused them and tested a donation again. This time, the event was successfully sent to GA4."

> "In order to send Classy transaction events to your GA4 property, we recommend *pausing or deleting the FB_CONVERSIONS_API tags* if they are no longer in use. If those tags are still needed, we can explore potential workarounds."

### Google's March 2025 Notification
Official notification about automatic Google tag loading:
> "Currently, your Google Tag Manager container(s) (GTM-TGH83XK) sends events before loading a Google tag. Starting April 10, 2025, containers with Google Ads and Floodlight tags will automatically load a Google tag first, before sending events."

> "This small change improves the reliability of your Google Ads tracking and will not harm measurement performance. For many users, it will increase the volume of measurement data."

Benefits outlined:
> "One-click access to features: Turn on features like Enhanced Conversions, Cross-domain tracking, and Autoevents easily from your Google tag settings page."

> "Smoother data collection: If you've agreed to our Customer Data Terms of Service, we'll automatically enable 'User Provided Data' collection across your events."

### Security Vulnerabilities (Google Tag Module)
From security notification in January 2025:
> "The module doesn't have the 'restrict access' flag on the 'administer google_tag_container' permission. A user with this permission can load a GTM container that completely changes the page or inserts malicious JS."

> "The module doesn't sufficiently validate the enabling or disabling of a tag container. The routes involved are not protected against Cross Site Request Forgery (CSRF)."

### Classy Platform Update (November 2024)
> "We updated our Google Analytics 4 and Google Tag Manager integrations to provide better insights for Classy Studio and Giving Cart campaigns. These include new variables, triggers, conversion events, and an import template for Google Tag Manager. We also released new support for Tealium to extend our analytics capabilities."

### Self-Assessment (March 2025)
> "To be honest, GTM is not my strong point. I pretty much configure tags according to the default instructions and check that they are operational. I have not really spent a lot of time optimizing those tags as that is its own field of expertise."

## 11. Key Documentation Dates

- **May 15, 2025:** GTM Tracking Reset document created
- **May 9, 2025:** Community Boost email about Classy transaction tracking issues
- **March 10, 2025:** Google notification about GTM changes effective April 10, 2025
- **January 29, 2025:** Security alerts for Google Tag module
- **November 13, 2024:** Classy platform updates including GTM integration improvements
- **October 30, 2024:** Security alert for Cookiebot + GTM module
- **December 16, 2024:** Kalamuna recommendation to use GTM for SiteImprove script