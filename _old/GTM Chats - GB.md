Chats



ConversationsResults in direct messages and spaces

Sort by most relevant

![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Apr 29, 11:56 AM

,

You: SFZC Website Analytics Improvement: Management Update
Progress Report
We've successfully identified and addressed the issue with our website's high 404 error rate in Google Analytics:

**Problem Identified**: We discovered Google Analytics was reporting 82% of our traffic as 404 errors, which was highly concerning.
**Root Cause Found**: Through New Relic server analysis, we determined the actual 404 error rate is only 13.6%. The discrepancy was caused by:
Google Tag Manager tracking error pages alongside normal pages
Bot traffic being counted in our analytics
Google Analytics tracking its own requests (/g/collect)

**Solution Implemented**: We made a simple configuration change to Google Tag Manager that restricts tracking to only successful page loads (status code 200).
**Verification Process**: We've established baseline metrics and created a filtered report to monitor improvement over the coming week.

Key Findings
**Not a User Experience Issue**: Greenflare crawler confirmed there are no significant broken internal links affecting real users.
**Primarily a Tracking Configuration Issue**: The problem was with our analytics setup, not with actual website content or structure.
**Expected Improvement**: 404 error percentage should drop from 82% to approximately 13-14% in our reports within the next few days.

Next Steps
**Monitor & Verify** (Next 7 days): Daily review of analytics reports to confirm the configuration change is working as expected.
**Resource Fixes** (2-3 weeks): Address missing favicon.ico and touch icons identified in the Greenflare scan.
**Enhanced Filtering** (3-4 weeks): Implement additional bot filtering in Google Analytics 4 to further improve data quality.
**Proactive Monitoring** (Ongoing): Schedule monthly Greenflare crawls to proactively identify any new broken links before they affect users.
**Documentation** (1 week): Complete technical documentation of the issue resolution for future reference.

This low-risk solution allows us to get more accurate analytics data without any changes to website functionality. We'll provide a follow-up report in one week with the final results. Show less

,

Apr 29, 11:56 AM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

Edited,,

May 7, 5:33 PM

,

You: Looks good. I will need to research the installation method for GTM. I will give it a look over on Friday and let you know what I find.

,

May 7, 5:33 PM

,Edited,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 17, 6:23 PM

,

You: Hi Dan - GTM appears to be working again. The GTM console debug screen attached shows it connected and firing its triggers properly. Give it a little time and check with GA to verify you are getting data as expected.

I also see that GTM is still showing untagged URLs. It turns out most of the ones on [SFZC.org](http://sfzc.org/) are either missing pages or not published correctly. I got rid of the obvious ones, but there are still 18 untagged URLs (mostly on [blogs.sfzc.org](http://blogs.sfzc.org/)). I will check into the rest later. Show less

Screenshot 2024-07-17 at 6.03.22 PM (2).png

,

Jul 17, 6:23 PM

,![Screenshot 2024-07-17 at 6.03.22 PM (2)](/Users/sfzcwebops/Desktop/Screenshot 2024-07-17 at 6.03.22 PM (2).png)



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Nov 8, 1:50 PM

,

You: **UPDATE - Drupal/****Google** **Tag** **Manager****: Missing on** [**SFZC.org**](http://sfzc.org/) **- FIXED (Please check)**

Hi Dan - I believe we have restored Google Tag Manager on [SFZC.org](http://sfzc.org/) (see attached GTM screenshot that shows tags firing). Have anyone concerned check it out.

It looks like the GTM module was updated to a new version and for some reason didn't bring our config data with it. Show less

2024-11-08_13-21-02.png

,

Nov 8, 1:50 PM

,![2024-11-08_13-21-02](/Users/sfzcwebops/Desktop/2024-11-08_13-21-02.png)



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

Edited,,

Oct 31, 4:07 PM

,

You: … Tag Manager). I checked, and it seems that the Google Tag Manager (GTM) module is no longer installed on our site. I looked at an older multi-dev site and, GTM was there. Instead … Show more

,

Oct 31, 4:07 PM

,Edited,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Nov 8, 2:21 PM

,

You: … everything is sorted and the right info is making it to GA. I just make sure the GTM script is showing up on the website and the config is right and the tags are firing in the GTM manager. Show more

2024-11-08_14-12-52.png

,

Nov 8, 2:21 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 25, 11:45 AM

,

I just finished meeting with Belen and Dan Gudgel - it was a good meeting about the GTM tags and more. I'm wondering if it would be possible to give Belen and Dan G. access to our Google Tag Manager so they can help … Show more

,

Jul 25, 11:45 AM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 23, 4:24 PM

,

You: **Google Ads Conversion Tracker - Config on** **Google** **Tag** **Manager**
Hi Dan - Regarding getting this tag going in GTM:
**Conversion ID**: This looks OK. I got it from Belen's tracking tag email 
**Conversion Label**: This is *required*, but I don't know where to find it's value
**Triggering**: Is "All Pages" OK or are there specific pages that should be triggered?

*See screenshot* Show less

google ads conversion tracker - config.png

,

Jul 23, 4:24 PM

![google ads conversion tracker - config](/Users/sfzcwebops/Desktop/google ads conversion tracker - config.png),

![screenshot-tagmanager.google.com-2024.07.24-13_01_21 (1)](/Users/sfzcwebops/Desktop/screenshot-tagmanager.google.com-2024.07.24-13_01_21 (1).png)

![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 25, 12:53 PM

,

You: GTM invites sent

,

Jul 25, 12:53 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

Edited,,

Oct 18, 1:33 PM

,

Hi Greg - I just bcc-d you on an email with Dan G. It looks like we might have a similar issue to something that happened a little while ago: the GA or GTM tag may have been removed from [sfzc.org](http://sfzc.org/) with a recent update to the website (possibly made by Kalamuna). Is this something you could check out? Show less

,

Oct 18, 1:33 PM

,Edited,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 24, 1:07 PM

,

You: Hi Dan - I installed the **Google Ads Conversion Tracking** in **GTM** (see screenshots). Everything looks good, but I don't know how to test that particular tag or under what circumstances it fires so I will leave it to you guys to determine if it is functioning correctly. Show less

screenshot-tagmanager.google.com-2024.07.24-13_01_21.png

,

Jul 24, 1:07 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Aug 9, 2:53 PM

,

Thanks Greg - yes, 100% no expectation for you around Analytics beyond GTM basics

,

Aug 9, 2:53 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 25, 11:48 AM

,

You: I don't mind. I would just need to know what changes they made. They can document that in GTM's version manager.

,

Jul 25, 11:48 AM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 18, 2:54 PM

,

You: Hi Dan - The TB Mega Menu module is installed on the LIVE site, but it is not running the drop-down menus. I am wondering if that drop-down code got caught up in the GTM update.

,

Jul 18, 2:54 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Now

,

You:  Hi Dan - Just a quick FYI for when you are working with the GTM audit: It's perfectly fine to attach emails, documents and other files to the audit. That way you don't have to do as much writing. The AI assistant is good at taking raw info and sorting it. 






![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Apr 29, 11:56 AM

,

You: SFZC Website Analytics Improvement: Management Update
Progress Report
We've successfully identified and addressed the issue with our website's high 404 error rate in Google Analytics:

**Problem Identified**: We discovered Google Analytics was reporting 82% of our traffic as 404 errors, which was highly concerning.
**Root Cause Found**: Through New Relic server analysis, we determined the actual 404 error rate is only 13.6%. The discrepancy was caused by:
Google Tag Manager tracking error pages alongside normal pages
Bot traffic being counted in our analytics
Google Analytics tracking its own requests (/g/collect)

**Solution Implemented**: We made a simple configuration change to Google Tag Manager that restricts tracking to only successful page loads (status code 200).
**Verification Process**: We've established baseline metrics and created a filtered report to monitor improvement over the coming week.

Key Findings
**Not a User Experience Issue**: Greenflare crawler confirmed there are no significant broken internal links affecting real users.
**Primarily a Tracking Configuration Issue**: The problem was with our analytics setup, not with actual website content or structure.
**Expected Improvement**: 404 error percentage should drop from 82% to approximately 13-14% in our reports within the next few days.

Next Steps
**Monitor & Verify** (Next 7 days): Daily review of analytics reports to confirm the configuration change is working as expected.
**Resource Fixes** (2-3 weeks): Address missing favicon.ico and touch icons identified in the Greenflare scan.
**Enhanced Filtering** (3-4 weeks): Implement additional bot filtering in Google Analytics 4 to further improve data quality.
**Proactive Monitoring** (Ongoing): Schedule monthly Greenflare crawls to proactively identify any new broken links before they affect users.
**Documentation** (1 week): Complete technical documentation of the issue resolution for future reference.

This low-risk solution allows us to get more accurate analytics data without any changes to website functionality. We'll provide a follow-up report in one week with the final results. Show less

,

Apr 29, 11:56 AM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Nov 8, 1:50 PM

,

You: **UPDATE - Drupal/****Google** **Tag** **Manager****: Missing on** [**SFZC.org**](http://sfzc.org/) **- FIXED (Please check)**

Hi Dan - I believe we have restored Google Tag Manager on [SFZC.org](http://sfzc.org/) (see attached GTM screenshot that shows tags firing). Have anyone concerned check it out.

It looks like the GTM module was updated to a new version and for some reason didn't bring our config data with it. Show less

2024-11-08_13-21-02.png

,

Nov 8, 1:50 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 23, 4:24 PM

,

You: **Google** **Ads Conversion Tracker - Config on** **Google** **Tag** **Manager**
Hi Dan - Regarding getting this tag going in GTM:
**Conversion ID**: This looks OK. I got it from Belen's tracking tag email 
**Conversion Label**: This is *required*, but I don't know where to find it's value
**Triggering**: Is "All Pages" OK or are there specific pages that should be triggered?

*See screenshot* Show less

google ads conversion tracker - config.png

,

Jul 23, 4:24 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

Edited,,

Oct 31, 4:07 PM

,

You: 

Hi Dan - 

Here's a message I sent to day to David at Kalamuna on Slack about moving forward with outstanding Drupal items. Just an FYI for you. We can talk details at our next check-in meeting on Tuesday.

Thanks!

\---

**REQUEST TO SCHEDULE TIME FOR DRUPAL OPS WORK WITH SFZC WEBOPS**

Hi David -
I would like to set up some time with you to move forward with some items with our internal Drupal ops project:

Dan has approved 10 hours for this work, and we will pre-pay upon getting the invoice.

Here are the main items I would like to cover with you:

**1.** **Google** **Tag** **Manager** **Missing (urgent)**
I posted a message about this on Slack the week before last and have not heard back so I will repeat it here:

I got a message from our Comms folk that they have not been getting any Google analytics from our site for the last few weeks (that data is normally handled by GoogleTagManager). I checked, and it seems that the GoogleTagManager (GTM) module is no longer installed on our site. I looked at an older multi-dev site and, GTM was there. Instead, there now seems to be a GoogleTag module on LIVE that I don't remember being there before. This issue seems to have coincided with the deployment of TBMM in mid-September.

This is a fairly important issue to resolve as soon as possible as we currently have contractors working on an analytics project for us, and they have not been able to get any data from the 

[SFZC.org](http://sfzc.org/)

 site since mid-September.
**

2. Finish Configuration Work**

I would like to finish the work we started in August with updating the configuration on LIVE with that on GitHub.

a. We left off with getting me permission to push commits to GitHub. That would need to be resolved before proceeding.
b. The config for LIVE has changed somewhat since we started this project in August. It might be necessary to start over with a recent local DEV version of the site.

**3. Drupal Core Update**
I would like to work with you to do a security update to the Drupal core (currently 10.2.6) to the recommended version, 10.3.6.

**4. Module Updates**
There are also a number of modules with available updates. We might pick several to do in person, while the rest I could do on my own afterward.

\-

Let me know if you have any questions or need clarification on any of the above.

My schedule is pretty wide open, so let me know what would work with you to schedule these sessions.

Thanks much! Show less

,

Oct 31, 4:07 PM

,Edited,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Apr 25, 5:26 PM

,

You: Hi Dan - I filled out my responses for the DT production workflow form so you can see an example before we talk about it on Tuesday...

Dharma Talk Production Workflow Documentation - Google Forms.pdf

,

Apr 25, 5:26 PM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 25, 11:45 AM

,

I just finished meeting with Belen and Dan Gudgel - it was a good meeting about the GTM tags and more. I'm wondering if it would be possible to give Belen and Dan G. access to our Google Tag Manager so they can help work on refining and adding tags in-line with the work they are doing? 

My first thought is that this would be okay to do since I don't think a tag can do anything like break a website (although I could be wrong), and Dan G has prior professional experience with GTM. Also it would free up your time from needing to do some of this! Curious what your thoughts are on this?  Thanks Show less

,

Jul 25, 11:45 AM

,



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

,

Jul 24, 1:07 PM

,

You: Hi Dan - I installed the **Google** **Ads Conversion Tracking** in **GTM** (see screenshots). Everything looks good, but I don't know how to test that particular tag or under what circumstances it fires so I will leave it to you guys to determine if it is functioning correctly. Show less

screenshot-tagmanager.google.com-2024.07.24-13_01_21.png

,

Jul 24, 1:07 PM

![screenshot-tagmanager.google.com-2024.07.24-13_01_21](/Users/sfzcwebops/Desktop/screenshot-tagmanager.google.com-2024.07.24-13_01_21.png),



![img](https://lh3.googleusercontent.com/a-/ALV-UjXu52QayicHWroBQ_hqwcCBhpHT19UF4mV3yB4PHqNbqRMqNEuc=s28-w28-h28-c-k-no)

Away

Dan Belsky

![screenshot-tagmanager.google.com-2024.07.24-13_02_06](/Users/sfzcwebops/Desktop/screenshot-tagmanager.google.com-2024.07.24-13_02_06.png)
